# Synthetic Policy: Insurance Premium Determination

## 1. Objective
The purpose of this policy is to determine the **annual insurance premium** for a policyholder by evaluating the **risk profile**, **coverage characteristics**, and **historical behavior** of the applicant.

The final price is computed as:

**Final Premium = Base Premium × Risk Multipliers − Discounts + Surcharges**

---

## 2. Base Premium Determination

The **base premium** depends on the **type of insurance product** and the **coverage amount**.

| Insurance Type | Coverage Amount | Base Premium |
|---|---|---|
| Auto | < €20,000 | €350 |
| Auto | €20,000 – €50,000 | €500 |
| Auto | > €50,000 | €750 |
| Home | < €200,000 | €300 |
| Home | €200,000 – €500,000 | €450 |
| Home | > €500,000 | €650 |
| Health | Individual | €600 |
| Health | Family | €1,100 |

---

## 3. Risk Multipliers

Risk multipliers reflect the **expected probability of claims**.

### 3.1 Age Risk (Auto Insurance)

| Driver Age | Multiplier |
|---|---|
| < 25 | 1.5 |
| 25–60 | 1.0 |
| > 60 | 1.2 |

### 3.2 Location Risk

| Area Risk Level | Multiplier |
|---|---|
| Low | 0.9 |
| Medium | 1.0 |
| High | 1.3 |

### 3.3 Claim History

| Claims in Last 3 Years | Multiplier |
|---|---|
| 0 | 0.8 |
| 1 | 1.0 |
| 2 | 1.2 |
| ≥ 3 | 1.5 |

---

## 4. Coverage Adjustments

### 4.1 Deductible Adjustment

| Deductible | Adjustment |
|---|---|
| < €250 | +20% |
| €250 – €500 | +10% |
| €500 – €1000 | 0% |
| > €1000 | −10% |

### 4.2 Optional Coverage Add-ons

| Add-on | Additional Cost |
|---|---|
| Roadside Assistance | €40 |
| Rental Car Coverage | €60 |
| Flood Protection | €75 |
| Identity Theft Protection | €50 |

---

## 5. Discounts

| Condition | Discount |
|---|---|
| Multi-policy (≥2 policies) | 10% |
| No claims in last 5 years | 15% |
| Safety certification (home alarms / driver training) | 5% |
| Automatic payment enrollment | 3% |

**Maximum cumulative discount:** 25%

---

## 6. Surcharges

| Condition | Surcharge |
|---|---|
| Fraud alert on previous policy | +30% |
| Payment default in last 2 years | +15% |
| Policy lapse > 60 days | +10% |

---

## 7. Final Premium Calculation

1. Determine **Base Premium**
2. Apply **Risk Multipliers**
