# Decision Assistant Hub

The **Decision Assistant Hub** is the companion repository to the [Decision Assistant](#), an AI-powered assistant that helps users turn business policies into structured decision models like rulesets and DMN diagrams.

This hub provides **curated examples**, **tutorials**, **tips**, and **video walkthroughs** to help you understand how to work with the assistant and apply it to real-world decision automation scenarios.
  

## Purpose

This repository is for:
- Learning how to convert natural language policies into formalized decision models
- Exploring domain-specific examples with rule outputs
- Watching guided walkthroughs and demos
- Getting tips, prompt ideas, and modeling strategies

---

## Repository Structure

| Folder | Description |
|--------|-------------|
| `examples/` | Sample business policies and their automated decision models, organized by domain |
| `docs/` | Getting started guides, tips, and FAQs |
| `media/` | Screenshots and video walkthroughs |
| `tutorials/` | Step-by-step usage guides |
| `CONTRIBUTING.md` | Guidelines for contributing new examples or content |

---

## Example Use Cases by Domain

Explore real-world scenarios where decision automation helps formalize and operationalize business logic:

### HR
- **[Time Off](examples/hr/time_off_policy/)**  
  Automate leave types, accruals, eligibility, and carryover logic.  
- **[Performance Bonus](examples/hr/performance_bonus_policy/)**  
  Rules to determine bonus eligibility based on performance tiers and seniority.

### Finance
- **[Expense Approval](examples/finance/expense_approval/)**  
  Multi-level approval rules and threshold-based routing using a decision table.

### Compliance
- **[Anti-Money Laundering (AML)](examples/compliance/aml_policy/)**  
  Transaction pattern rules and risk classification logic.  
<!-- - **[Know Your Customer (KYC)](examples/compliance/kyc_policy/)**  
  Decision logic for onboarding, document verification, and customer risk scoring. -->

### Operations
- **[Vendor Risk Scoring](examples/operations/vendor_risk_scoring/)**  
  Model for supplier assessment using weighted risk attributes and thresholds.

---

## Get Started

1. Make sure you're set up with the **Decision Assistant**
2. Browse the `examples/` folder by domain to find a scenario similar to yours.
3. Read the `policy.md`, then explore the generated rules (`rules.md`, `.json`, or `.dmn`).
4. Watch demo videos in [`media/videos/`](media/videos/).


<!-- ## Learn by Doing

Start with one of these tutorials:

- 📘 [Using the Assistant to Extract Rules](tutorials/01_using_the_assistant.md)
- 🛠️ [Refining and Editing the Generated Models](tutorials/02_editing_generated_models.md)

--- -->

## [`Practical Guide to writing Policies`](docs/tips_and_tricks.md)

---

## ❓ FAQ: [`docs/faq.md`](docs/faq.md)


<!-- ## Media

- [Demo Walkthrough](media/videos/demo_walkthrough.mp4)
- [From Policy to Rules – Explained](media/videos/from_policy_to_rules.mp4)

--- -->

## Contributing

We welcome contributions!

[`Click Here`](CONTRIBUTING.md) for guidelines.

---

## License

This project is licensed under the **Apache 2.0**.

---

<!-- ## Contact

Have a use case to showcase?  
Open an issue or start a [discussion](https://github.com/your-org/decision-assistant-hub/discussions) — we'd love to hear from you! -->
