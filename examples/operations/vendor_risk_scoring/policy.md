To evaluate and manage third-party risk, Acme Corp employs a weighted scoring model that classifies vendors based on their risk exposure. The model considers multiple risk attributes and applies predefined thresholds to determine risk levels and mitigation requirements.
## 1. Scoring Model Overview
Vendor risk is assessed using the following weighted attributes:
| Risk Attribute             | Weight (%) | Description                                                                |
| -------------------------- | ---------- | -------------------------------------------------------------------------- |
| **Operational Dependency** | 25%        | Criticality of the vendor’s service or product to Acme Corp’s operations.  |
| **Data Sensitivity**       | 20%        | Nature and volume of Acme’s data handled by the vendor (e.g., PII, IP).    |
| **Geographic Exposure**    | 15%        | Location of operations and legal jurisdiction, including country risk.     |
| **Cybersecurity Maturity** | 15%        | Strength of vendor’s security controls, certifications, and audit history. |
| **Regulatory Impact**      | 10%        | Compliance burden associated with the vendor relationship.                 |
| **Financial Health**       | 10%        | Vendor’s financial viability based on credit ratings or financial reports. |
| **Reputation/ESG**         | 5%         | Known controversies, ESG scores, or negative media coverage.               |
> **Note**: Attribute weights are reviewed annually and may be adjusted based on evolving risk posture.
## 2. Scoring Method
Each vendor is scored from **1 to 5** per attribute, where:
| Score | Meaning                          |
| ----- | -------------------------------- |
| 1     | Very Low Risk / Highly Favorable |
| 2     | Low Risk                         |
| 3     | Moderate Risk                    |
| 4     | High Risk                        |
| 5     | Very High Risk / Unacceptable    |
A weighted score is then computed as the sum of `(attribute weight × attribute score)` across all attributes.
## 3. Risk Classification Thresholds
Based on the final weighted score (ranging from 1.0 to 5.0), vendors are placed into one of three risk categories:
| Final Score Range | Risk Level  | Required Actions                                        |
| ----------------- | ----------- | ------------------------------------------------------- |
| **1.0 – 2.4**     | Low Risk    | Standard due diligence; monitor annually.               |
| **2.5 – 3.4**     | Medium Risk | Enhanced due diligence; semi-annual risk review.        |
| **3.5 – 5.0**     | High Risk   | Executive sign-off, mitigation plan, quarterly reviews. |
> Vendors scoring **5 in any single attribute** may be subject to **automatic escalation**, even if their total weighted score is below the high-risk threshold.
## 4. Assessment Frequency
* **New Vendors**: Full assessment required prior to onboarding.
* **Existing Vendors**:
  * Low Risk: Annual reassessment
  * Medium Risk: Every 6 months
  * High Risk: Every quarter, or more frequently if flagged.
## 5. Exceptions and Overrides
* Compliance or Legal may override the final score based on external risk intelligence, audit findings, or contract terms.
* In urgent situations, a **provisional approval** may be granted pending full risk review, for up to **90 days**.