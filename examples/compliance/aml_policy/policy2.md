# ACME CORP – Anti–Money Laundering and Counter–Terrorist Financing Policy - 2


---

## 1. Purpose
This policy defines the measures taken by Acme Corp to detect and prevent money laundering and terrorist financing in accordance with French and EU regulations. It applies to all business units, channels, and customer types.

---

## 2. Customer Risk Classification

| Risk Level  | Criteria |
|-------------|----------|
| **Standard** | Customer has verified identity (full KYC), conducts domestic activity, and has predictable transactions consistent with their profile. |
| **Elevated** | Customer is in a high-risk industry, frequently sends or receives foreign wire transfers, has incomplete KYC, or displays unusual transaction behavior. |

The Compliance team may override this classification based on alerts, investigation results, or professional judgment.

---

## 3. Data Requirements

### 3.1 Customer Data
- Unique customer ID
- Type (natural person or legal entity)
- KYC status
- PEP status (including relatives and close associates)
- Industry and high-risk sector flag
- Risk level
- Country of residence
- Onboarding date

### 3.2 Account Data
- Unique account ID
- Linked customer ID
- Currency
- Account status
- Opening date

### 3.3 Transaction Data
- Transaction ID
- Linked account ID
- Timestamp
- Direction (inbound/outbound)
- Amount and currency (plus amount in EUR)
- Payment method
- Channel
- Origin country, destination country, counterparty bank country
- Purpose code
- Whether the transaction is part of a repeated pattern

### 3.4 Reference Lists
- EU sanctions list (countries and entities)
- FATF high-risk country list
- Embargoed countries list

---

## 4. Transaction Monitoring

Acme Corp monitors all customer transactions in real time and through periodic batch processing to identify potential money laundering or terrorist financing activity.

All transactions are converted to their EUR equivalent using the exchange rate on the transaction date for threshold calculations. Monitoring covers all payment methods (bank transfers, card payments, cash, cheques, crypto-assets, and others) and all channels (branch, online, mobile, ATM, API).

The following situations require review and possible escalation:

| Scenario | Description | Minimum Action |
|----------|-------------|----------------|
| **Large transactions** | Any transaction ≥ €10,000 | Manual review |
| **Cash by occasional customer** | Cash transaction ≥ €1,000 by a customer without an ongoing relationship | Flag and verify ID |
| **Structuring** | ≥ 3 transactions within 7 days just below reporting thresholds (€9,000–€9,999 or €2,900–€2,999) with totals above thresholds | Manual review |
| **Rapid movement of funds** | Inbound transaction ≥ €5,000 followed by outbound totaling ≥ 80% of inbound amount within 48 hours from same account | Manual review |
| **Sanctioned country/entity** | Any transaction involving a country or entity on EU sanctions lists | Block if legally permitted; escalate immediately |
| **High-risk country** | Any transaction involving a FATF high-risk jurisdiction | Enhanced Due Diligence and manual review |
| **Dormant account activity** | Account inactive ≥ 180 days with transaction ≥ €1,000 | Manual review |
| **Activity spike** | Volume in last 7 days ≥ 3× average weekly volume over last 8 weeks | Manual review |
| **Unusual channel/method** | Transaction ≥ €2,000 using a method or channel outside customer's normal patterns | Manual review |
| **High-risk counterparty** | Transaction ≥ €1,000 with counterparty in high-risk industry | Manual review |

A whitelist of approved recurring transactions (e.g., payroll, rent) may suppress alerts if all approved parameters match and the whitelist is still valid. Each whitelist entry has an expiry date and is subject to periodic review.

---

## 5. Alert Handling

- Alerts related to sanctions or embargoes are treated as **critical** and acted upon immediately.
- Alerts involving high-risk countries or structuring are treated as **high** severity.
- Unusual methods or counterparties are generally **medium** severity.
- All alerts, including those suppressed by a whitelist, are logged with trigger details and reviewer identity.
- Suppressed alerts must record the whitelist entry used and its expiry date.

---

## 6. Escalation and Reporting

When suspicion remains after review:
1. Compliance creates or updates an investigation case.
2. A Suspicious Transaction Report (STR) is filed with TRACFIN within 24 working hours.
3. Additional measures may include account restrictions, freezes, or Enhanced Due Diligence.

---

## 7. Record Keeping

- All KYC data, transaction records, and alert handling logs are retained for 5 years after the end of the business relationship.
- Records must be easily retrievable for audits by regulators.

---

## 8. Governance and Training

- Annual mandatory AML/LCB-FT training for relevant staff.
- Quarterly compliance committee review of monitoring results, emerging risks, and rule effectiveness.

---
