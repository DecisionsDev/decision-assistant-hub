# Telecom Offer Recommendation Policy --- Decision Automation 201 (Extraction‑Optimized)

## 1. Purpose

This policy describes how telecom offers are recommended.

Objectives: - Ensure regulatory and commercial compliance - Maintain
transparent and explainable recommendations - Prioritize eligible offers
based on campaigns and operational constraints

------------------------------------------------------------------------

## 2. Reference Data

### 2.1 Countries

  Country Code   Country Name    Market Zone
  -------------- --------------- ---------------
  NLD            Netherlands     EU
  BEL            Belgium         EU
  LUX            Luxembourg      EU
  FRA            France          EU
  USA            United States   International
  CAN            Canada          International
  IND            India           International
  KOR            South Korea     International
  ZAF            South Africa    International

------------------------------------------------------------------------

### 2.2 Telecom Offers

  ------------------------------------------------------------------------------------------
  Offer ID Offer Name   Offer     Risk Class  Allowed     Min        Stock    Campaign Tag
                        Type                  Countries   Contract   Status   
  -------- ------------ --------- ----------- ----------- ---------- -------- --------------
  T-100    Student 5G   Mobile    Standard    NLD, BEL,   12M        High     BackToSchool
           Plan         Plan                  LUX, FRA                        

  T-200    Smartwatch   Add-on    Standard    NLD, BEL,   1M         Medium   SummerBoost
           eSIM Add-on                        LUX, FRA,                       
                                              USA, CAN,                       
                                              IND, ZAF                        

  T-300    Business     Mobile    Regulated   NLD, BEL,   24M        High     None
           Secure SIM   Plan                  FRA                             

  T-400    Travel Data  Roaming   Standard    NLD, BEL,   0M         Low      SummerBoost
           Pack                               LUX, FRA,                       
                                              KOR, USA,                       
                                              CAN, IND                        

  T-500    Premium      Mobile    Standard    NLD, BEL,   12M        High     None
           Unlimited 5G Plan                  LUX, FRA                        
  ------------------------------------------------------------------------------------------

------------------------------------------------------------------------

### 2.3 Customer Segments

  Segment    Description
  ---------- -----------------------------
  Student    Verified education customer
  Standard   Retail subscriber
  Premium    High-value or loyalty tier

------------------------------------------------------------------------

### 2.4 Account Attributes

  Attribute            Possible Values
  -------------------- -------------------------------
  accountStatus        Active, Suspended
  verificationStatus   Verified, Missing
  creditCategory       LowRisk, MediumRisk, HighRisk

------------------------------------------------------------------------

## 3. Decision Model Structure

The automation evaluates offers in the following fixed order:

1.  Account Eligibility\
2.  Regulatory Eligibility\
3.  Country Eligibility\
4.  Credit and Contract Eligibility\
5.  Operational Eligibility (Stock)\
6.  Campaign Priority\
7.  Final Priority Assignment

If an offer is excluded at any step, later steps MUST NOT change its
status.

------------------------------------------------------------------------

## 3.1 Decision Output Contract

Each offer evaluation produces:

-   OfferDecisionStatus = Recommended \| Excluded\
-   PriorityLevel = High \| Normal \| None\
-   ReasonCodes\[\]

Testing Rules:

-   Excluded offers MUST have PriorityLevel = None.
-   Recommended offers MUST include at least one reason code.
-   If a campaign increases priority, ReasonCodes MUST include
    CAMPAIGN_BOOST.
-   If no specific rule increases priority, ReasonCodes MUST include
    ELIGIBLE_STANDARD.

------------------------------------------------------------------------

## 4. Eligibility Rules

### Account Status

-   If accountStatus is Suspended, the offer is Excluded with
    ACCOUNT_SUSPENDED.

### Age and Regulation

-   If customerAge is under 18 and Risk Class is Regulated, the offer is
    Excluded.
-   If Risk Class is Regulated and verificationStatus is Missing, the
    offer is Excluded with VERIFICATION_REQUIRED.

### Country Eligibility

-   If customerCountry is not listed in Allowed Countries, the offer is
    Excluded.
-   EU customers (NLD, BEL, LUX, FRA) may receive EU offers when listed.
-   International customers (USA, CAN, IND, KOR, ZAF) may only receive
    offers explicitly listing their country.
-   Regulated offers are limited to listed EU countries only.
-   When excluded by country rules, ReasonCodes MUST include
    COUNTRY_NOT_ALLOWED and PriorityLevel = None.

### Credit and Contract

-   If creditCategory is HighRisk and Min Contract is 12M or more, the
    offer is Excluded with CREDIT_RISK_BLOCK.

If no exclusion applies, the offer becomes Eligible.

------------------------------------------------------------------------

## 5. Operational Rules

-   If Stock Status = Low\
    → OfferDecisionStatus = Excluded\
    → ReasonCodes include LOW_STOCK\
    → PriorityLevel = None

-   If Stock Status = Medium\
    → Offer remains Eligible\
    → Default Priority = Normal

-   If Stock Status = High\
    → Offer becomes Promotion Eligible\
    → Default Priority = High

Operational exclusions override campaign rules.

------------------------------------------------------------------------

## 6. Campaign Priority Rules

Campaign Priority Boost is applied when:

-   activeCampaign matches Offer Campaign Tag, AND
-   any required segment condition is satisfied.

Effects of Campaign Priority Boost:

-   PriorityLevel becomes High.
-   ReasonCodes MUST include CAMPAIGN_BOOST.

Campaign rules never change eligibility.

------------------------------------------------------------------------

## 7. Priority Assignment Rules

High Priority: - Eligible AND Stock Status = High, OR - Campaign
Priority Boost applies.

Normal Priority: - Eligible AND Stock Status = Medium AND no campaign
boost applies.

Excluded offers always have PriorityLevel = None.

------------------------------------------------------------------------

## 8. Decision Outputs

Each offer evaluation must produce:

-   OfferDecisionStatus
-   PriorityLevel
-   ReasonCodes\[\]

Standard Reason Codes:

-   ACCOUNT_SUSPENDED
-   COUNTRY_NOT_ALLOWED
-   VERIFICATION_REQUIRED
-   CREDIT_RISK_BLOCK
-   LOW_STOCK
-   CAMPAIGN_BOOST
-   ELIGIBLE_STANDARD

------------------------------------------------------------------------

## 9. Governance

-   Marketing manages campaigns and offer targeting.
-   Compliance manages regulatory classifications.
-   Operations manages stock status.
-   Commercial teams manage contract rules.

All policy versions must be traceable.

------------------------------------------------------------------------

## 10. Testing Assumptions

-   Each offer is evaluated independently.
-   Priority is assigned only to Recommended offers.
-   Multiple reason codes may be returned.
-   Order of reason codes is not significant.
-   Campaign rules never remove an exclusion.

------------------------------------------------------------------------

## 11. Example Scenario

### Customer Profile

  Attribute            Value
  -------------------- --------------
  customerSegment      Student
  customerAge          20
  accountStatus        Active
  verificationStatus   Verified
  creditCategory       LowRisk
  customerCountry      FRA
  activeCampaign       BackToSchool

### Expected Outcome

-   T-100 → Recommended (High Priority)
-   T-200 → Recommended (Normal Priority)
-   T-300 → Recommended (High Priority)
-   T-400 → Excluded (LOW_STOCK)
-   T-500 → Recommended (High Priority)

------------------------------------------------------------------------

## 12. Version

Policy Version: 3.1 --- Decision Automation 201
