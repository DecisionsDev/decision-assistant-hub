# Acme Transactions

# Real-Time Fraud Decision Policy

**Policy ID:** ATX-FRAUD-001\
**Version:** 1.0\
**Effective Date:** 2026-03-02\
**Applies To:** All payment transactions processed by Acme Transactions\
**Objective:** Produce a real-time decision: `APPROVE`, `CHALLENGE`,
`REVIEW`, or `DECLINE`

------------------------------------------------------------------------

## 1. Overview

This policy defines the deterministic rules and risk-scoring model used
by Acme Transactions to evaluate payment transactions for potential
fraud.

The policy is automation-ready and designed for integration into a
real-time decision engine.

## 2. Required Inputs

### 2.1 Transaction Data

-   `tx_id` (string)
-   `amount` (number)
-   `currency` (string)
-   `timestamp_utc` (ISO 8601 string)
-   `merchant_id` (string)
-   `mcc` (string)
-   `channel` (enum: `CARD_PRESENT`, `ECOM`, `MOTO`, `RECURRING`)
-   `country` (ISO2 string)
-   `city` (optional string)

### 2.2 Account Context

-   `account_age_days` (integer)
-   `card_status` (enum: `ACTIVE`, `SUSPENDED`, `LOST`, `STOLEN`)
-   `prior_confirmed_fraud_90d` (boolean)
-   `avg_daily_spend_30d` (number)
-   `home_country` (ISO2 string)

### 2.3 Derived Features (Computed by System)

-   `tx_count_10m` (integer)
-   `tx_count_1h` (integer)
-   `spend_24h` (number)
-   `distinct_countries_2h` (integer)
-   `device_first_seen_days` (integer, optional)
-   `ip_country` (string, optional)
-   `vpn_or_tor` (boolean, optional)

### 2.4 Merchant Risk Profile

-   `merchant_risk` (enum: `LOW`, `MEDIUM`, `HIGH`)
-   `merchant_chargeback_rate_90d` (number, optional)

## 3. Output Contract

The fraud engine must return:

-   `decision` (enum: `APPROVE`, `CHALLENGE`, `REVIEW`, `DECLINE`)
-   `risk_score` (integer 0--1000)
-   `reasons` (array of rule codes with descriptions)
-   `recommended_actions` (array of enums:\
    `STEP_UP_AUTH`, `NOTIFY_USER`, `TEMPORARY_HOLD`, `CASE_CREATE`)

## 4. Hard Block Rules (Immediate Decline)

If any condition below evaluates to TRUE, the transaction must be
immediately `DECLINE`d.

### HB-1

If `card_status IN {LOST, STOLEN}`

### HB-2

If `prior_confirmed_fraud_90d = true AND amount > 50`

### HB-3

If `tx_count_10m >= 10`

When triggered: - `decision = DECLINE` - `risk_score = 1000` - Include
triggered rule(s) in `reasons`

## 5. Risk Scoring Model

If no Hard Block is triggered:

1.  Initialize `risk_score = 0`
2.  Add points for each triggered rule
3.  Clamp final score to range `[0,1000]`

### 5.1 Velocity & Spending Rules

  Rule   Condition                               Points
  ------ --------------------------------------- --------
  R-1    `tx_count_10m >= 5`                     +220
  R-2    `tx_count_1h >= 12`                     +180
  R-3    `spend_24h > 3 * avg_daily_spend_30d`   +200
  R-4    `amount > 2 * avg_daily_spend_30d`      +120

### 5.2 Geographic Risk Rules

  Rule   Condition                                             Points
  ------ ----------------------------------------------------- --------
  R-5    `distinct_countries_2h >= 2`                          +260
  R-6    `country != home_country`                             +80
  R-7    `channel IN {ECOM, MOTO} AND ip_country != country`   +120

### 5.3 Device & Network Rules

  --------------------------------------------------------------------------------------------------
  Rule             Condition                                                   Points
  ---------------- ----------------------------------------------------------- ---------------------
  R-8              `channel IN {ECOM, MOTO} AND device_first_seen_days <= 1`   +140

  R-9              `channel IN {ECOM, MOTO} AND vpn_or_tor = true`             +220
  --------------------------------------------------------------------------------------------------

### 5.4 Merchant Risk Rules

  Rule   Condition                                 Points
  ------ ----------------------------------------- --------
  R-10   `merchant_risk = HIGH`                    +220
  R-11   `merchant_risk = MEDIUM`                  +90
  R-12   `merchant_chargeback_rate_90d >= 0.009`   +120

### 5.5 Account Risk Rules

  Rule   Condition                 Points
  ------ ------------------------- --------
  R-13   `account_age_days < 30`   +120
  R-14   `account_age_days < 7`    +180

**Conflict Rule:**\
If both R-13 and R-14 are applicable, apply only the higher score
(R-14).

## 6. Decision Thresholds

  Risk Score Range   Decision
  ------------------ -----------
  `< 350`            APPROVE
  `350 – 649`        CHALLENGE
  `650 – 849`        REVIEW
  `>= 850`           DECLINE

## 7. Action Mapping

  Decision    Recommended Actions
  ----------- ------------------------------------------------
  APPROVE     \[\]
  CHALLENGE   `STEP_UP_AUTH`, `NOTIFY_USER`
  REVIEW      `CASE_CREATE`, `TEMPORARY_HOLD`, `NOTIFY_USER`
  DECLINE     `NOTIFY_USER`, `CASE_CREATE`

If `STEP_UP_AUTH` fails or times out → escalate to `DECLINE`.

## 8. Governance & Versioning

-   Policy must be versioned and immutable once deployed.
-   Changes to scoring weights or thresholds require a new version ID.
-   All decisions must log:
    -   Input snapshot
    -   Triggered rules
    -   Final score
    -   Final decision

**End of Policy -- ATX-FRAUD-001**
