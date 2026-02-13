# Product Recommendation Policy — Decision Automation 201

## 1. Purpose
This policy defines how products are recommended to customers using clear business rules.  
The objective is to ensure that every recommendation is appropriate, compliant, and aligned with current business campaigns, while remaining fully explainable.

This policy is intentionally rule-based. Recommendations are determined by explicit conditions and not by predictive models, machine learning, or probabilistic scoring.

## 2. Policy Overview
Products may be recommended only when they meet all eligibility and operational requirements.  
Campaigns may increase the visibility or priority of certain products, but they must never override safety or eligibility rules.

The recommendation decision follows three principles:
- Only eligible products can be recommended.
- Campaigns influence priority, not eligibility.
- Operational constraints such as stock availability must always be respected.

## 3. Customer Eligibility
A product must not be recommended if the customer account is suspended.  
Products classified as regulated must not be recommended to customers who are under eighteen years old or whose verification status is missing.

Recommendations must respect geographic restrictions. If a product is not allowed in the customer’s country, it must be excluded from the recommendation list.

When none of the exclusion conditions apply, the product is considered eligible for recommendation.

## 4. Campaign Alignment
When a campaign is active, products associated with that campaign may receive higher priority in the recommendation list.

For example, student-oriented products may be prioritised during a BackToSchool campaign when the customer belongs to a student segment.  
Similarly, products tagged for a seasonal promotion may be highlighted when that promotion is active.

If no campaign applies, products are recommended with normal priority.

## 5. Inventory Constraints
Products with low stock must not be recommended.  
Products with medium stock levels may be recommended normally.  
Products with high stock levels may be promoted with increased visibility.

Inventory rules always take precedence over promotional objectives.

## 6. Final Recommendation Decision
A product is excluded from recommendation if it fails eligibility checks or inventory constraints.

If a product is eligible and inventory levels are high, it should be recommended with high priority.  
If a product is eligible and linked to an active campaign, it should also receive high priority.

All other eligible products may be recommended with normal priority.

## 7. Decision Outputs
Each recommendation decision must produce:
- A list of recommended products
- A list of excluded products
- A priority level indicating recommendation strength
- Clear reason codes explaining why a product was included or excluded

The explanation must be understandable to business users and traceable to a specific rule.

## 8. Governance
Business owners are responsible for maintaining eligibility rules, campaign definitions, and inventory thresholds.  
All changes to this policy must be versioned to ensure traceability over time.

## 9. Version
Policy Version: 1.0  
