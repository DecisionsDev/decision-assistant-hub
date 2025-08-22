## Tip 1: Avoid Double Quotes for Enum Types

**Issue:**  
Enum values like `Vacation` or `SickLeave` were written as `"Vacation"` and `"SickLeave"`, which treats them as strings instead of enum literals.

**Why it's a problem:**  
BAL expects enum values to be referenced directly. Using quotes causes type mismatches and may lead to incorrect rule behavior.

**Correction:**  
Remove the double quotes and use the enum values directly.

**Demo Video:**  
[Watch the demo](videos/tips_and_tricks/tip_1.mp4)

--- 

## Tip 2: Do Not Use `of <Class>` with Boolean Fields

**Issue:**  
Boolean fields were written using the `of <Class>` construct, such as `isOnPip of EmployeePerformance`, which is invalid syntax in BAL.

**Why it's a problem:**  
BAL does not support the `of <Class>` syntax for boolean fields. This results in a syntax error during rule validation or execution.

**Correction:**  
Reference boolean fields directly without the class context.

**Demo Video:**  
[Watch the demo](videos/tips_and_tricks/tip_2.mp4)

---

## Tip 3: Default Rules Should Not Have Conditions

**Issue:**  
A rule marked as the default (fallback) includes a condition, such as `meetsCriteria is false`.

**Why it's a problem:**  
In BAL, default rules are meant to execute only when no other conditions are met. Including a condition in a default rule causes a syntax error and defeats the purpose of having a fallback.

**Correction:**  
Remove all conditions from default rules. The rule should only contain the action to be taken.

**Demo Video:**  
[Watch the demo](videos/tips_and_tricks/tip_3.mp4)

---
