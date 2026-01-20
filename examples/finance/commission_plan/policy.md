# Sales Commission Policy

**Effective Date:** January 1st 2026  
**Applies To:** All Sales Representatives  
**Owner:** Sales Operations (with Finance oversight)  
**Reviewed By:** Finance, Legal, HR  

---

## 1. Purpose
This policy defines how sales commissions and new account opening incentives are calculated and paid, ensuring transparency, fairness, and auditability.

---

## 2. Definitions

- **Quota (Q):** The sales revenue target assigned to a Sales Representative for a measurement period.
- **Transaction Value (TV):** The booked value of an individual transaction before any recognition adjustments.
- **Transaction Type:** One of **Software**, **Subscription**, **Services**.
- **Sales Channel:** **Direct** or **Indirect**.
- **Recognized Revenue (RR):** The transaction value multiplied by the applicable recognition rate based on the transaction type and channel.
- **Quota Attainment (%):** Recognized revenue for the period divided by the representative's quota.
- **New Account Transaction:** A transaction attributed to a customer account with first revenue posted in the current measurement period.

---

## 3. Recognized Revenue Calculation

| Transaction Type | Direct Rate | Indirect Rate |
|------------------|-----------:|-------------:|
| Software         | 100%       | 70%          |
| Subscription     | 200%       | 140%         |
| Services         | 80%        | 60%          |

**Formula:**  
```
RR_tx = TV_tx × RecognitionRate(type, channel)
RR_period = Σ RR_tx (for all transactions in the period)
```

---

## 4. Commission Rates by Quota Attainment

| Attainment Band       | Commission Rate |
|------------------------|-----------------:|
| 0% – 50%              | 1.0%            |
| >50% – 80%            | 1.5%            |
| >80% – 100%           | 2.0%            |
| >100% – 150%          | 3.0%            |
| >150% – 200%          | 4.0%            |
| >200%                 | 4.5%            |

**Commission per transaction:**  
```
Commission_tx = TV_tx × CommissionRate(band_at_posting)
```

---

## 5. New Account Opening Bonus

| New Account Transactions | Bonus |
|---------------------------|------:|
| 1 – 5                    | $250  |
| 6 – 10                   | $400  |
| >10                      | $500  |

---

## 6. Worked Example

**Example:**  
- Quota: $200,000  
- Transaction: $50,000 Direct Subscription  
- RR = 50,000 × 200% = $100,000  
- Attainment = 100,000 / 200,000 = 50% → Commission Rate = 1.0%  
- Commission = 50,000 × 1.0% = $500  

---

## 7. Edge Cases & Clarifications
- Band inclusivity: 0–50% includes 50%, etc.
- Zero quota defaults to lowest band (1.0%).
- Split credit applies proportionally to TV and RR.
- Adjustments processed in the period recognized.
- Rounding: Commission rounded to nearest cent.

---

## 9. Governance
- Payment after period close.
- Disputes within 30 days.
- Adjustments processed next cycle.

---

## 10. Policy Changes
Company may update this policy; latest version supersedes prior versions. 