## Tip 1: Avoid Double Quotes for Enum Types

**Issue:**  
Enum values like `Vacation` or `SickLeave` were written as `"Vacation"` and `"SickLeave"`, which treats them as strings instead of enum literals.

**Why it's a problem:**  
BAL expects enum values to be referenced directly. Using quotes causes type mismatches and may lead to incorrect rule behavior.

**Correction:**  
Remove the double quotes and use the enum values directly.

**Demo Video:**  
[Watch the demo](https://decisionsdev.github.io/decision-assistant-hub/videos/syntax_errors_fixes/tip_1)

--- 

## Tip 2: Do Not Use `of <Class>` with Boolean Fields

**Issue:**  
Boolean fields were written using the `of <Class>` construct, such as `isOnPip of EmployeePerformance`, which is invalid syntax in BAL.

**Why it's a problem:**  
BAL does not support the `of <Class>` syntax for boolean fields. This results in a syntax error during rule validation or execution.

**Correction:**  
Reference boolean fields directly without the class context.

**Demo Video:**  
[Watch the demo](https://decisionsdev.github.io/decision-assistant-hub/videos/syntax_errors_fixes/tip_2/tip_2.mp4)

---

## Tip 3: Default Rules Should Not Have Conditions

**Issue:**  
A rule marked as the default (fallback) includes a condition, such as `meetsCriteria is false`.

**Why it's a problem:**  
In BAL, default rules are meant to execute only when no other conditions are met. Including a condition in a default rule causes a syntax error and defeats the purpose of having a fallback.

**Correction:**  
Remove all conditions from default rules. The rule should only contain the action to be taken.

**Demo Video:**  
[Watch the demo](https://decisionsdev.github.io/decision-assistant-hub/videos/syntax_errors_fixes/tip_3/tip_3.mp4)

---

## Tip 4: Use the Article "the" Before Non-Boolean Variables

**Issue:**  
Non-boolean variables were referenced without the article "the", such as `employmentStatus` instead of `the employmentStatus`.

**Why it's a problem:**  
BAL syntax requires the article "the" before non-boolean variables. Omitting it results in a syntax error.

**Correction:**  
Always use "the" before non-boolean variables.


**Demo Video:**  
[Watch the demo](https://decisionsdev.github.io/decision-assistant-hub/videos/syntax_errors_fixes/tip_4/tip_4.mp4)

## Tip 5: Do Not Use "the" Before Boolean Variables

**Issue:**  
Boolean variables were written with the article "the", such as `the isOnPip`, which is invalid syntax in BAL.

**Why it's a problem:**  
BAL syntax does not allow the article "the" before boolean variables. Including it causes a syntax error.

**Correction:**  
Reference boolean variables directly without using "the".

**Demo Video:**  
[Watch the demo](https://decisionsdev.github.io/decision-assistant-hub/videos/syntax_errors_fixes/tip_5/tip_5.mp4)

---

## Tip 6: Dates Must Be in MM/DD/YYYY Format

**Issue:**  
Dates were written in formats like `DD-MM-YYYY`, `YYYY/MM/DD`, or descriptive formats such as `Jan 1, 2025`. These are all invalid in BAL.

**Why it's a problem:**  
BAL strictly requires dates to be in the `MM/DD/YYYY` format. Any other format will result in a syntax error or incorrect parsing.

**Correction:**  
Always write dates in the `MM/DD/YYYY` format.

---

## Tip 7: Rules for Collections and Lists

### 1. Use Plural Form for Collection Variables

**Issue:**  
Collection variables were referenced using singular names, such as `employee` instead of `employees`.

**Why it's a problem:**  
BAL requires the plural form when referring to collections. Using the singular form causes a syntax error.

**Correction:**  
Use the plural form of the variable name.

**Incorrect:**
```bal
employee includes "John"
```

**Correct:**
```bal
employees includes "John"
```

---

### 2. Use `{}` Instead of `[]` for Lists

**Issue:**  
Lists were written using square brackets (`[]`), which is invalid in BAL.

**Why it's a problem:**  
BAL uses curly braces (`{}`) to define lists. Square brackets are not recognized and will cause a syntax error.

**Correction:**  
Use curly braces for lists.

**Incorrect:**
```bal
employees includes ["John", "Jane"]
```

**Correct:**
```bal
employees includes {"John", "Jane"}
```

---

### 3. Represent Empty Lists as `{ ' ' }`

**Issue:**  
Empty lists were written as `{}`, which is invalid in BAL.

**Why it's a problem:**  
BAL requires empty lists to be represented as `{ ' ' }`. Using `{}` will result in a syntax error.

**Correction:**  
Use `{ ' ' }` to represent an empty list.


**Demo Video:**  
[Watch the demo](https://decisionsdev.github.io/decision-assistant-hub/videos/syntax_errors_fixes/tip_7/tip_7.mp4)

---

## Tip 8: Use Double Quotes for String Literals

**Issue:**  
String values were written without double quotes, such as `Vacation` instead of `"Vacation"`.

**Why it's a problem:**  
BAL requires string literals to be enclosed in double quotes. Omitting the quotes causes a syntax error or misinterpretation of the value.

**Correction:**  
Always use double quotes around string literals.

**Incorrect:**
```bal
reason is Vacation
```

**Correct:**
```bal
reason is "Vacation"
```
