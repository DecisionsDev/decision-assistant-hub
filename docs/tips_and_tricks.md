# ✅ Tips for Writing Decision Assistant-Friendly Policies

## 1. **Use Clear Section Headings**

Break your policy into well-titled sections like:

* `Eligibility`
* `Approval Logic`
* `Risk Tiers`
* `Thresholds & Exceptions`

**Why:** Decision Assistant use these headers to anchor meaning and separate logic domains.

---

## 2. **Use Tables for Thresholds and Decision Logic**

Whenever your policy includes thresholds, conditions, or routing logic, **express it as a table**.

**✅ Example:**

```
| Expense Amount     | Expense Type        | Required Approvers         |
|--------------------|---------------------|-----------------------------|
| ≤ $500             | Any                 | Direct Manager              |
| $501 – $2,000      | Travel              | Manager + Finance Reviewer  |
```

**Why:** Tables reduce ambiguity and make comparison easy for the Assistant.

---

## 3. **Make Conditional Logic Explicit**

Use **IF–THEN–ELSE** patterns when describing rule flows or dependencies.

**✅ Example:**

> If the vendor handles customer PII, then a data protection agreement (DPA) is required. Otherwise, standard terms apply.

**Avoid:**

> Vendors with sensitive data need extra agreements. *(Too vague.)*

---

## 4. **Be Consistent with Terminology**

Define terms once and use them **consistently** across the document.

* Don’t switch between “staff” and “employee”
* Don’t alternate between “bonus” and “incentive” unless they mean different things

**✅ Tip:** Include a **Glossary** for important terms like:

* Low/Medium/High Risk
* Eligible Employee
* Sanctioned Jurisdiction

---

## 5. **Quantify Wherever Possible**

Use measurable language instead of qualitative terms.

**✅ Use:**

* “More than \$10,000”
* “Within 30 days of purchase”
* “4 out of 5 risk categories must be low”

**Avoid:**

* “A significant amount”
* “Timely manner”
* “Usually safe”

---

## 6. **Avoid Nested Ambiguities**

When writing exceptions or overrides, avoid stacking too many conditions in a single sentence.

**✅ Clear:**

> Employees hired before 2004 and with 20+ years of service receive 5 weeks of vacation.

**❌ Ambiguous:**

> Employees with 20+ years or hired before 2004 get extra time.

---

## 7. **Separate Policy from Justification**

Keep **what the rule is** and **why it exists** in different sentences or sections.

**✅ Example:**

> Laptops must be purchased through IT. This ensures device compliance and asset tracking.

**Why:** Decision Assistant can distinguish the rule (enforceable) from context (explanatory).

---

## 8. **List Exceptions in a Dedicated Section**

Rather than sprinkling exceptions throughout the policy, create an **"Exceptions and Escalations"** section.

**✅ Example:**

> Any deviation from this policy must be approved by Finance and documented via email.

---

## 9. **Use Bullet Points for Enumerations**

Whenever there’s a list of conditions, steps, or factors, use bullet points.

**✅ Example:**
Risk scoring is based on:

* Geographic origin
* Data sensitivity
* Transaction velocity

---

## 10. **Label Optional, Mandatory, and Discretionary Elements**

Indicate whether rules are required or flexible.

**✅ Use Tags:**

* `[Mandatory]`
* `[Optional]`
* `[Manager Discretion]`

---

# ✍️ Bonus: Writing Checklist

| Feature                       | ✓ Check |
| ----------------------------- | ------- |
| Clear section headings        |         |
| Structured tables             |         |
| Consistent terminology        |         |
| Explicit conditionals         |         |
| Measurable thresholds         |         |
| Exceptions isolated           |         |
| Definitions or glossary added |         |
| Justifications separated      |         |

---
