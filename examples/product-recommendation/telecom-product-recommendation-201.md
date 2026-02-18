# Telecom Offer Recommendation Policy — Decision Automation 201

## 1. Purpose
This policy defines how telecom plans and add-ons are recommended using deterministic business rules.

Objectives:
- Ensure regulatory and commercial compliance
- Maintain transparent and explainable recommendations
- Prioritize eligible offers based on campaigns and operational constraints

No machine learning, scoring models, or probabilistic ranking are used.

---

## 2. Reference Data

### 2.1 Countries

| Country Code | Country Name   | Market Zone    |
|-------------|----------------|----------------|
| NLD         | Netherlands    | EU             |
| BEL         | Belgium        | EU             |
| LUX         | Luxembourg     | EU             |
| KOR         | South Korea    | International  |
| ZAF         | South Africa   | International  |

---

### 2.2 Telecom Offers

| Offer ID | Offer Name              | Offer Type   | Risk Class | Allowed Countries       | Min Contract | Stock Status | Campaign Tag  |
|---------|--------------------------|-------------|-----------|-------------------------|-------------|-------------|--------------|
| T-100   | Student 5G Plan          | Mobile Plan | Standard  | NLD, BEL, LUX           | 12M         | High        | BackToSchool |
| T-200   | Smartwatch eSIM Add-on   | Add-on      | Standard  | NLD, BEL, LUX, ZAF      | 1M          | Medium      | SummerBoost  |
| T-300   | Business Secure SIM      | Mobile Plan | Regulated | NLD, BEL                | 24M         | High        | None         |
| T-400   | Travel Data Pack         | Roaming     | Standard  | NLD, BEL, LUX, KOR      | 0M          | Low         | SummerBoost  |
| T-500   | Premium Unlimited 5G     | Mobile Plan | Standard  | NLD, BEL, LUX           | 12M         | High        | None         |

---

### 2.3 Customer Segments

| Segment  | Description                    |
|----------|--------------------------------|
| Student  | Verified education customer    |
| Standard | Retail subscriber              |
| Premium  | High-value or loyalty tier     |

---

### 2.4 Account Attributes

| Attribute           | Possible Values                     |
|--------------------|--------------------------------------|
| accountStatus       | Active, Suspended                    |
| verificationStatus  | Verified, Missing                    |
| creditCategory      | LowRisk, MediumRisk, HighRisk        |

---

## 3. Policy Overview
Offer recommendation follows three evaluation phases:
1. Eligibility Validation
2. Campaign & Pricing Priority
3. Operational Constraints

Processing is sequential. Rules defined earlier may exclude an offer from later evaluation.

---

## 4. Eligibility Rules
An offer MUST be excluded when any condition below is true:
- accountStatus = Suspended
- customerAge < 18 AND Risk Class = Regulated
- Risk Class = Regulated AND verificationStatus = Missing
- customerCountry NOT IN Allowed Countries
- creditCategory = HighRisk AND Min Contract >= 12M

If none apply, the offer is **Eligible**.

Example:
Offer T-300 (Business Secure SIM) is regulated and only allowed in Netherlands and Belgium.
Customers located in Luxembourg must not receive this offer.

---

## 5. Campaign and Pricing Priority Rules
Campaign rules influence priority but NEVER override eligibility or operational rules.

### 5.1 BackToSchool Campaign
IF activeCampaign = BackToSchool  
AND customerSegment = Student  
AND Offer.CampaignTag = BackToSchool  
THEN apply Priority Boost.

### 5.2 SummerBoost Campaign
IF activeCampaign = SummerBoost  
AND Offer.CampaignTag = SummerBoost  
THEN increase visibility for all segments.

### 5.3 Standard Behavior
IF no campaign applies  
THEN offer retains Normal Priority.

---

## 6. Inventory and Operational Rules
Stock Status represents operational readiness:
- Stock Status = Low -> MUST be excluded.
- Stock Status = Medium -> Eligible with Normal Priority.
- Stock Status = High -> Eligible with Promotion Capability.

Operational rules always override campaign rules.

Example:
T-400 (Travel Data Pack) has Low stock and must be excluded even during SummerBoost.

---

## 7. Final Recommendation Logic

### 7.1 Exclusion
Offer is excluded when:
- Eligibility fails, OR
- Stock Status = Low.

### 7.2 High Priority Recommendation
Offer receives High Priority when:
- Eligible AND Stock Status = High, OR
- Campaign Priority Boost is applied.

### 7.3 Normal Priority Recommendation
Offer receives Normal Priority when:
- Eligible AND Stock Status = Medium, AND
- No campaign boost applies.

---

## 8. Decision Outputs
Each evaluation must produce:
- RecommendedOffers[]
- ExcludedOffers[]
- PriorityLevel per Offer
- ReasonCodes[]

Standard Reason Codes:
- ACCOUNT_SUSPENDED
- COUNTRY_NOT_ALLOWED
- VERIFICATION_REQUIRED
- CREDIT_RISK_BLOCK
- LOW_STOCK
- CAMPAIGN_BOOST
- ELIGIBLE_STANDARD

---

## 9. Governance
Business ownership:
- Marketing maintains campaign tags and eligibility
- Compliance maintains Risk Class definitions
- Operations maintains Stock Status thresholds
- Commercial teams maintain contract duration rules

All policy changes must be versioned for auditability.

---

## 10. Example Scenario

### Customer Profile

| Attribute           | Value        |
|--------------------|--------------|
| customerSegment     | Student      |
| customerAge         | 20           |
| accountStatus       | Active       |
| verificationStatus  | Verified     |
| creditCategory      | LowRisk      |
| customerCountry     | NLD          |
| activeCampaign      | BackToSchool |

### Expected Outcome
- T-100 -> Recommended (High Priority) due to campaign + high stock
- T-200 -> Recommended (Normal Priority)
- T-300 -> Recommended (High Priority)
- T-400 -> Excluded (Low Stock)
- T-500 -> Recommended (High Priority)

---

## 11. Version
Policy Version: 2.1 — Telecom Domain (Real Countries)
