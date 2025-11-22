---
sidebar_position: 3
slug: /chapter-2-sdd
---

# Chapter 2: Principles of Spec-Driven Development

## What is a Spec?

In SDD, a **Specification** is not a vague Jira ticket or a dusty Confluence page. 
It is a **rigorous, structured document** that serves as the prompt for the AI.
It acts as the contract between the Architect (You) and the Builder (AI).

## The 4 Pillars of a Good Spec

1.  **Context:** What is the surrounding system? (e.g., "This is a Next.js app using Tailwind.")
2.  **Intent:** What should this specific component do? (e.g., "A button that debounces clicks and calls API X.")
3.  **Constraints:** What are the non-negotiables? (e.g., "Must be accessible (WCAG AA), must use Zod for validation.")
4.  **Examples:** Show, don't just tell. (e.g., "Input: 'abc', Output: Error 'Too short'.")

## The SDD Workflow

### Step 1: The Skeleton Spec
Start with a high-level outline.
```markdown
# Component: UserProfile
- Display user avatar, name, and bio.
- Allow editing bio.
- Persist to Supabase.
```

### Step 2: AI Interrogation
Ask the AI to critique the spec.
> "Review this spec. What edge cases am I missing? What security risks exist?"

The AI might reply: "You didn't specify max length for bio, or what happens if the avatar image fails to load."

### Step 3: Refinement
Update the spec with the AI's feedback.
```markdown
# Component: UserProfile
...
- Bio: Max 500 chars, sanitize HTML.
- Avatar: Fallback to initials if image fails.
```

### Step 4: Generation
Now, and only now, ask the AI to generate the code.
> "Implement the UserProfile component based on the above spec."

### Step 5: Verification
Run the code. Does it meet the spec?
If not, **do not fix the code manually**. Fix the prompt/spec and regenerate.
This enforces discipline and ensures the spec remains the source of truth.

## Conclusion
SDD forces you to think before you code. It shifts the effort upstream, where it is cheaper to fix mistakes.
