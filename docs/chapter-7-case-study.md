---
sidebar_position: 8
slug: /chapter-7-case-study
---

# Chapter 7: Real-World Case Study: The Enterprise Platform

## The Mission

Let's build a **Distributed Task Scheduler** (like a mini-Celery) using SDD.

## Phase 1: The Spec
We start by writing `scheduler-spec.md`.
```markdown
# Distributed Scheduler Spec
- **Goal:** Execute async tasks with retries.
- **Stack:** Node.js, Redis, PostgreSQL.
- **Components:**
  - Producer API (REST)
  - Worker Nodes (Consumer)
  - Dashboard (Next.js)
- **Constraints:**
  - At-least-once delivery.
  - Max 3 retries with exponential backoff.
```

## Phase 2: Architecture Generation
We ask the AI: "Generate a folder structure and `docker-compose.yml` for this spec."
The AI scaffolds the repo.

## Phase 3: Component Implementation
We iterate component by component.
**Prompt:** "Implement the Redis consumer in `worker/src/consumer.ts`. Use `ioredis`. Handle connection failures gracefully."
**Verification:** We run the worker. It crashes on connection loss.
**Refinement:** "The worker crashed. Add a reconnection strategy with 5s delay."

## Phase 4: The Dashboard
**Prompt:** "Generate a Next.js page that lists active tasks from the Postgres DB. Use a table component."
**Result:** A basic table.
**Refinement:** "Add a 'Retry' button to the failed tasks."

## Lessons Learned
- **Iterative Refinement:** You rarely get it right on the first prompt.
- **Context Management:** We had to remind the AI about the "Max 3 retries" constraint when it implemented the worker.
- **Speed:** We built a working prototype in 4 hours, a task that usually takes 3 days.

## Summary
- Start with a solid spec.
- Build iteratively.
- Verify constantly.
