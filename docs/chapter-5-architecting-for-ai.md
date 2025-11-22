---
sidebar_position: 6
slug: /chapter-5-architecting-for-ai
---

# Chapter 5: Architecting for AI

## Designing for the Model

We used to design code for human readability. Now we must also design for **Model Readability**.
LLMs thrive on context, but they suffer from "lost in the middle" phenomenon.
Your architecture should maximize the signal-to-noise ratio for the AI.

## Principles of AI-Friendly Architecture

### 1. Radical Modularity
Small, self-contained functions and classes are easier for an AI to understand, test, and modify.
- **Bad:** A 500-line `UserController`.
- **Good:** `CreateUser`, `UpdateUser`, `DeleteUser` as separate, single-purpose functions/files.

### 2. Strong Typing as Guardrails
Types (TypeScript, Rust, Java) act as a rigid skeleton.
If the AI hallucinates a method that doesn't exist, the compiler catches it immediately.
**Type-Driven Development** pairs perfectly with AI. You define the types; the AI fills the implementation.

### 3. Explicit Interfaces
Define clear boundaries between components.
Use Interface Definition Languages (IDLs) or OpenAPI specs.
This allows the AI to mock dependencies easily and understand how systems interact without reading every line of code.

### 4. Self-Documenting Code
Comments are more important than ever.
Not `// increments i`, but `// This function calculates tax based on the 2024 US tax code using the bracket method.`
These comments serve as "mini-prompts" for the AI when it modifies the code later.

## The "Context Window" Optimization

Treat your codebase like a database.
Optimize for retrieval.
- Use consistent naming conventions.
- Colocate related files (e.g., `Button.tsx`, `Button.test.tsx`, `Button.stories.tsx`).
- Keep directory depth shallow.

## Summary
- Architecture dictates AI performance.
- Use types to constrain the AI's search space.
- Write code that explains itself to the model.
