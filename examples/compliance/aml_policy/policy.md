*Acme Corp Compliance Division*
This document outlines key rules and guidelines for monitoring transaction patterns and classifying customer risk for AML compliance purposes. These standards are intended to help identify potentially suspicious activity while allowing flexibility for business judgment.
## 1. Transaction Pattern Monitoring
Acme Corp monitors customer transactions for behaviors that deviate from expected financial activity based on known customer profiles.
### Trigger Rules (Indicative, Not Exhaustive)
Transactions may be flagged for AML review if they meet one or more of the following patterns:
* **High-Volume Transfers**:
  * Multiple transfers above \$10,000 within a rolling 7-day period.
  * Three or more cash deposits over \$7,500 in one calendar month.
* **Structured Transactions** (a.k.a. "Smurfing"):
  * Frequent cash deposits just under reporting thresholds (e.g., \$9,900).
  * Repeated fund transfers just below \$3,000 across different accounts.
* **Rapid Movement of Funds**:
  * Incoming transfers followed by outbound transfers of equal or near-equal amounts within 24–48 hours.
  * Incoming international wire transfers not followed by discernible business activity.
* **Geographic Risk Flags**:
  * Transactions originating from or routed through **sanctioned** or **high-risk jurisdictions**, as identified by OFAC or FATF watchlists.
* **Dormant Reactivation**:
  * Accounts with no activity for 180+ days that suddenly receive or send funds exceeding \$5,000.
> **Note**: A flagged transaction **does not imply wrongdoing** but will initiate review under internal compliance workflows.
## 2. Customer Risk Classification
Customers are evaluated for AML risk at onboarding and periodically thereafter. Risk classification influences the depth and frequency of transaction monitoring.
### Risk Levels
| Risk Tier       | Characteristics                                                                                                |
| --------------- | -------------------------------------------------------------------------------------------------------------- |
| **Low Risk**    | Verified ID, domestic activity, predictable volume, low cash handling.                                         |
| **Medium Risk** | Mixed transaction types, occasional foreign activity, moderate cash usage.                                     |
| **High Risk**   | Involvement in high-risk sectors (e.g., crypto, casinos), frequent foreign wires, inconsistent income sources. |
### Risk Assessment Factors
* **Customer Type**
  * Individuals vs. businesses vs. intermediaries (e.g., agents, brokers).
* **Industry Segment**
  * High-risk sectors include: gambling, real estate, international trade, NGOs, and virtual asset service providers.
* **Transaction Behavior**
  * High velocity or opaque transaction flows may elevate risk.
* **KYC Completeness**
  * Missing or unverifiable information increases risk score.
* **Jurisdictional Risk**
  * Residency, transaction origin/destination, and citizenship contribute to geographic risk weighting.
> Risk ratings may be overridden by compliance officers based on judgment or external alerts.
## 3. Review and Escalation
* All **high-risk transactions** are subject to manual review by a compliance analyst.
* **Medium-risk cases** may be reviewed periodically or based on trigger conditions.
* **Low-risk transactions** are typically handled via automated monitoring unless flagged.
* Patterns may be **whitelisted** if validated by customer history (e.g., payroll processing, tuition payments).
Escalations may lead to a **Suspicious Activity Report (SAR)** filing, account restrictions, or enhanced due diligence (EDD).