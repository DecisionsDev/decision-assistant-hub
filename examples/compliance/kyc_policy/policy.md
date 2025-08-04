Acme Corp follows a structured, risk-based approach to KYC as part of its customer onboarding process. This policy outlines the minimum standards for identity verification, documentation, and risk classification, subject to applicable laws and regulatory guidelines.
## 1. Onboarding Decision Logic
Customer onboarding outcomes depend on identity validation, documentation completeness, and preliminary risk assessment.
### Onboarding Pathways
| Customer Type                | Onboarding Method    | Notes                                                 |
| ---------------------------- | -------------------- | ----------------------------------------------------- |
| Individual (Domestic)        | Standard Online Flow | Auto-decisioning if all documents pass verification.  |
| Individual (Foreign)         | Enhanced Review      | Manual approval required for high-risk jurisdictions. |
| Entity (e.g., Business, NGO) | Tiered Due Diligence | Requires UBO (Ultimate Beneficial Owner) disclosures. |
> **Exception Handling**:
> If a customer cannot complete onboarding within 30 days due to documentation issues, the application is paused or withdrawn, unless compliance grants an extension.
## 2. Document Verification Requirements
Minimum documentation requirements vary by customer type and onboarding channel.
### Required Documents
| Document Type              | Individuals                        | Businesses / Entities                    |
| -------------------------- | ---------------------------------- | ---------------------------------------- |
| Government-issued ID       | Mandatory                          | Mandatory for UBOs                       |
| Proof of Address (≤ 3 mo)  | Mandatory (unless e-KYC validated) | Required for principal place of business |
| Business Registration Docs | N/A                                | Certificate of Incorporation, GST/Tax ID |
| Source of Funds Statement  | Optional for low-risk              | Required for medium/high-risk            |
### Verification Logic
* **Automated Verification**: Validates ID number, face match (if selfie provided), and document expiration.
* **Manual Review Triggers**:
  * Mismatched name or gender.
  * Blurred or expired document.
  * Jurisdictional red flags.
> **Note**: ID must be valid at the time of submission; expired IDs will be rejected unless verified by a notary or equivalent authority.
## 3. Customer Risk Scoring
Customers are assigned a risk score during onboarding. The score determines the level of monitoring and due diligence throughout the relationship.
### Risk Score Tiers
| Risk Tier       | Description & Criteria                                                                  |
| --------------- | --------------------------------------------------------------------------------------- |
| **Low Risk**    | Domestic customer, verified documents, low transaction expectations.                    |
| **Medium Risk** | Foreign national or small business with moderate transaction volume.                    |
| **High Risk**   | Complex ownership structures, politically exposed persons (PEPs), or high-risk country. |
### Scoring Inputs
* **Geographic Risk**: Based on country of residence, nationality, and source of funds.
* **Document Confidence**: Degree of match, recency, and system validation status.
* **Entity Complexity**: Number of UBOs, offshore links, and unclear ownership trails.
* **Customer Intent**: Based on stated purpose (e.g., personal savings vs. international remittance).
> A customer’s risk score may be updated post-onboarding based on transaction behavior, regulatory alerts, or internal reviews.
## 4. Conditional Approval and Watchlist Screening
* All customers are screened against **global sanctions and watchlists** (OFAC, UN, EU, etc.).
* **Conditional approval** may be granted for low-value accounts pending full document submission, provided no watchlist hit is found.
* **Hits** on politically exposed persons (PEPs), adverse media, or sanctions result in **automatic escalation** to compliance.