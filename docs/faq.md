# FAQ

## Getting Started

**Q:** What should I enter when getting started with the Decision Assistant?  
**A:** You can provide either:  
- **A decision theme** – a broad area like “Loan approvals” or “Employee onboarding.”  
- **A specific decision point** – a concrete, actionable decision like “Approve a loan for a customer with a credit score above 700” or “Determine discount eligibility for loyalty members.”

## Policy Input & Formatting

**Q:** What formats are supported for policies?  
**A:** Raw text in the assistant.

**Q:** How many words are supported for a policy?  
**A:** Up to 10,000 words.

**Q:** How should I format the policy?  
**A:** No specific formatting is required, but the assistant prefers markdown with clear headings and tables for better structure and readability.

## Decision Assistant Behavior

**Q:** Can I edit the decision model after it's generated?  
**A:** Yes, after every stage, if you're not satisfied, you get an option to provide feedback and refine the model.

**Q:** Can I use multiple policies for a single decision model?  
**A:** No, only one policy can be used per decision model.

**Q:** Why are not all decision points in the policy captured in the decision model?  
**A:** This depends on the complexity of the policy and the capability of the language model. Some decision points may be implicit, ambiguous, or too nuanced for automatic extraction.

**Q:** Why do I get different responses for the same input?  
**A:** This is an inherent behavior of the language model. It can generate varied responses based on subtle differences in context, phrasing, or randomness in generation.

**Q**: Why do I see errors in the rules?
**A**: Decision Assistant translates natural language derived from the policy into BAL rules. While the logic may be correctly understood, the generated BAL syntax may not always be accurate. These errors are due to limitations in the translation process and may require manual correction to ensure the rules are syntactically valid.
