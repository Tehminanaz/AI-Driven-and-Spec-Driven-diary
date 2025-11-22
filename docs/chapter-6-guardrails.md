---
sidebar_position: 7
slug: /chapter-6-guardrails
---

# Chapter 6: Guardrails & Quality Assurance

## Trust But Verify

The most dangerous assumption in AI development is that the model is right.
Models are probabilistic engines. They can be confidently wrong.
You need an **Immune System** for your codebase.

## The Layers of Defense

### 1. Static Analysis (Linting & Types)
The first line of defense.
- **ESLint/Prettier:** Enforce style so the AI doesn't drift.
- **TypeScript:** Enforce contracts.
- **Security Scanners:** Tools like Snyk or Semgrep to catch vulnerabilities (e.g., hardcoded keys) that AI might accidentally insert.

### 2. Automated Testing
AI is great at writing tests. Use that.
- **Unit Tests:** Verify individual functions.
- **Integration Tests:** Verify component interactions.
- **E2E Tests:** Verify the user flow.
**Rule:** No AI-generated code is merged without a passing test suite.

### 3. Formal Verification
For critical logic (e.g., payments, crypto), use formal methods or property-based testing (e.g., FastCheck).
Ask the AI to generate the properties: "Generate a property test to prove that `calculateDiscount` never returns a negative number."

## The Human Review
AI can review code, but humans must review the *design*.
Focus your code review on:
- **Security:** "Is this input sanitized?"
- **Performance:** "Is this O(n^2) loop necessary?"
- **Maintainability:** "Is this too complex?"

## Summary
- Build a fortress of automated checks.
- Use AI to write the tests that verify the AI.
- Shift human review to high-level architecture and security.
