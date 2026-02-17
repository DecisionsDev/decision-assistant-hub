# Product Recommendation Policy — Decision Automation 201

## 1. Purpose
This policy describes how products are recommended to customers using explicit business rules.  
The goal is to ensure that recommendations are eligible, safe, and aligned with active campaigns, while remaining fully explainable and deterministic.

All decisions defined in this policy are rule-based. No machine learning, AI scoring, or probabilistic ranking is used.

---

## 2. Synthetic Reference Data

The following synthetic values are used for illustration in this policy.

### 2.1 Countries
| Country Code | Country Name | Region |
|---|---|---|
| NLD | Noveria | EU |
| BEL | Belvaria | EU |
| LUX | Luxara | EU |
| ZAF | Zafron | International |
| KOR | Koralis | International |

---

### 2.2 Products
| Product ID | Product Name | Category | Risk Class | Allowed Countries | Stock Level | Campaign Tag |
|---|---|---|---|---|---|---|
| P-100 | Student Laptop Bundle | Electronics | Standard | NLD, BEL, LUX | High | BackToSchool |
| P-200 | Smart Fitness Watch | Wearables | Standard | NLD, BEL, LUX, ZAF | Medium | SummerSale |
| P-300 | SecurePay Card Reader | Finance Device | Regulated | NLD, BEL | High | None |
| P-400 | Travel Camera Kit | Electronics | Standard | NLD, BEL, LUX, KOR | Low | SummerSale |
| P-500 | Premium Noise Headphones | Audio | Standard | NLD, BEL, LUX | High | None |

---

### 2.3 Customer Segments
| Segment | Description |
|---|---|
| Student | Customer enrolled in education programs |
| Standard | Regular retail customer |
| Premium | Loyalty-based high-value customer |

---

## 3. Policy Overview
A product may be recommended only if it passes eligibility and operational checks.  
Campaigns influence the priority of recommendations but do not override compliance or safety constraints.

The decision follows three main evaluations:
1. Customer and product eligibility
2. Campaign alignment
3. Inventory availability

---

## 4. Eligibility Rules
A product must be excluded from recommendation when any of the following conditions apply:

- The customer account status is **Suspended**.
- The customer is under 18 years old and the product risk class is **Regulated**.
- The product is regulated and the customer verification status is **Missing**.
- The customer’s country is not listed in the product’s allowed countries.

If none of these conditions apply, the product is considered eligible.

**Example:**  
Product P-300 (SecurePay Card Reader) is regulated and only allowed in NLD and BEL.  
A customer from Luxara (LUX) must not receive this recommendation.

---

## 5. Campaign Alignment Rules
Campaigns increase the visibility of products that share the same campaign tag.

- During the **BackToSchool** campaign, products tagged BackToSchool may receive high priority for Student customers.
- During the **SummerSale** campaign, products tagged SummerSale may receive increased visibility for all segments.
- If no campaign applies, products retain normal priority.

**Example:**  
Product P-100 may be prioritised for Student customers during BackToSchool.

---

## 6. Inventory Rules
Operational constraints always apply:

- Products with **Low** stock must not be recommended.
- Products with **Medium** stock may be recommended normally.
- Products with **High** stock may be promoted with higher priority.

**Example:**  
Product P-400 has low stock and must be excluded regardless of campaign status.

---

## 7. Final Recommendation Logic
A product is excluded when:
- It is not eligible, or
- Inventory status is Low.

A product is recommended with **High Priority** when:
- It is eligible and stock level is High, or
- It matches an active campaign.

A product is recommended with **Normal Priority** when:
- It is eligible and inventory status is Medium, and
- No campaign rule increases its priority.

---

## 9. Decision Outputs
Each evaluation must produce:

- RecommendedProducts[]
- ExcludedProducts[]
- PriorityLevel
- ReasonCodes explaining which rules were applied

Example reason codes:
- COUNTRY_NOT_ALLOWED
- VERIFICATION_REQUIRED
- LOW_STOCK
- CAMPAIGN_MATCH
- ELIGIBLE_STANDARD

---

## 10. Governance
Business teams maintain:
- Country eligibility lists
- Product risk classifications
- Campaign tags
- Inventory thresholds

All policy changes must be versioned to ensure traceability and auditability.

---

## 8. Example Scenario

### Customer Profile
| Attribute | Value |
|---|---|
| customerSegment | Student |
| customerAge | 20 |
| accountStatus | Active |
| verificationStatus | Verified |
| customerCountry | NLD |
| activeCampaign | BackToSchool |

### Expected Outcome
- P-100 → Recommended (High Priority) due to campaign and high stock.
- P-200 → Recommended (Normal Priority).
- P-300 → Recommended (High Priority) because eligible and high stock.
- P-400 → Excluded due to low stock.
- P-500 → Recommended (High Priority) because stock is high.

---

## 11. Version
Policy Version: 1.0  
Decision Automation Level: 201 — Rule-Based Only
