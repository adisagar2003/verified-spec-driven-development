---
name: verified-spec-driven-development
description: Use when starting any new feature, project, or multi-step implementation before writing code — guides engineers through a structured spec-first, test-first workflow that leverages AI effectively while building real understanding
license: MIT
compatibility: Works with any AI coding assistant (Claude Code, Cursor, Windsurf, Copilot, ChatGPT)
metadata:
  author: aditya-sagar
  version: "1.0"
  tags: "methodology, tdd, spec-driven, ai-assisted-engineering"
---

# Verified Spec-Driven Development (VSDD)

A practical workflow for building software with AI assistance — without outsourcing your thinking.

AI makes you faster at every phase: understanding codebases, catching edge cases, generating implementations, reviewing code. But speed without understanding produces fragile software and engineers who can't debug their own work.

VSDD gives structure to when you think and when you delegate — so you build real skills while shipping real software.

> "Not all AI-powered coding is vibe coding." — Samuel Gregory

## When to Use

- Starting a new feature, project, or multi-step implementation
- Building anything with multiple layers (schema, API, UI)
- Working on data contracts, compliance, or cross-system integration
- Learning a codebase and building something meaningful in it

**Skip this for:** single-line fixes, formatting, dependency bumps, throwaway prototypes.

## The Workflow

### Step 1: Understand the Domain

Use AI to build your mental model fast. Don't wander through files blindly — ask for the big picture first, then drill into what matters.

**Useful prompts:**
- "Generate a mermaid diagram showing how the client and backend communicate and list the most important modules"
- "Explain the data model — what are the core entities and how do they relate?"
- "Walk me through what happens when a user does [specific action]"
- "What are the key files I should read to understand [area]?"

Then read those key files yourself. Ask follow-ups on anything unclear. Your goal: be able to sketch the architecture on a whiteboard from memory.

### Step 2: Write Your Spec

This is where *you* think through the problem. Write it yourself — it forces you to make decisions instead of deferring them.

**A spec answers:**
- What are the inputs, outputs, and core types?
- What are the edge cases and error states?
- How does this fit into the existing system?
- What does "done" look like?

**Then hand it to AI for review:**
- "What edge cases am I missing?"
- "Are there ambiguities or contradictions in this spec?"
- "What would break this design?"

Update based on findings. This loop — you write, AI stress-tests, you refine — is where specs get sharp.

### Step 3: Break It Into Layers

Every project has natural layers. Identify yours and build from the inside out:

```
Types/Schema → Validation → Adapters → Business Logic → API → UI
```

Create an issue or task for each layer. This is your roadmap — one layer at a time, each fully tested before moving on.

### Step 4: Build Each Layer Test-First

For each layer:

```
1. Write tests describing what it SHOULD do     (they fail — that's correct)
2. Write the minimal code to make tests pass     (no more than needed)
3. Refactor while tests stay green               (clean up, extract, simplify)
4. Move to the next layer
```

**AI accelerates this:**
- "Given this spec, what test cases should I cover for [layer]?"
- "Here's my failing test — generate an implementation"
- "How can I refactor this to be cleaner?"

You don't need to scrutinize every semicolon — but you should understand the approach and be able to explain why the code works, not just that it passes.

### Step 5: Get a Fresh Review

After each major layer, get a review from **fresh context** — a new AI session or a different model. The AI that helped you build shares your assumptions and blind spots.

**Give the reviewer only your spec + code:**
- "Does this implementation match the spec?"
- "What bugs, security issues, or gaps do you see?"
- "What did I miss?"

Route findings back to the right step:
- Spec gaps → Step 2
- Missing tests → Step 4
- Code issues → fix in place

### Step 6: Harden and Ship

Scale hardening to your project's risk level:

| Level | What to Do |
|-------|-----------|
| **Every project** | Linter, type checker, full test suite |
| **Most projects** | Fuzz test inputs (adapters, parsers, user data) |
| **High-stakes** | Security scan, mutation testing, load testing |

You're done when a fresh reviewer has to reach to find issues.

## When AI Helps vs When You Think

| Situation | AI Accelerates | You Own |
|-----------|---------------|---------|
| Exploring a codebase | Diagrams, summaries, architecture overviews | Choosing what to dig into |
| Designing the solution | Suggesting options and tradeoffs | Writing the spec — your decisions |
| Writing tests | Generating cases from your spec | Defining what "correct" means |
| Implementing | Generating code from failing tests | Reviewing logic and approach |
| Debugging | Explaining errors, suggesting causes | Understanding the root cause |
| Reviewing | Fresh-context critique | Triaging what matters |
| Architecture | Listing options with pros/cons | Making the call |

The pattern: AI generates options and catches gaps. You make decisions and maintain understanding.

## Staying on Track

Drifting into autopilot happens to everyone. A few gentle signals to pause and re-engage:

- **You can't explain what your code does** — Ask AI to walk you through it. Understanding takes a few minutes and saves hours of debugging later.
- **You're pasting errors back in a loop** — Read the error yourself first. Ask "what does this error mean?" instead of "fix this."
- **No spec or tests exist yet** — Normal if you just started. Write them before you build further.
- **You skipped the fresh review** — It's the single highest-value step. Even 10 minutes catches real issues.

These aren't failures — they're moments to slow down before continuing.

## Quick Reference

```
Understand (AI diagrams + exploration)
    → Spec (you write, AI reviews)
    → Break into layers
    → For each layer: Test → Implement → Refactor
    → Fresh review → Route feedback
    → Harden → Ship
```

## Background

VSDD adapts ideas from three sources:

| Source | Key Idea |
|--------|----------|
| [Verified Spec-Driven Development](https://gist.github.com/dollspace-gay/d8d3bc3ecf4188df049d7a4726bb2a00) | Six-phase spec-first, test-first, adversarially-refined pipeline |
| [AI-Assisted vs Vibe Coding](https://www.linkedin.com/pulse/vibe-coding-does-equal-ai-assisted-samuel-gregory-ec9wf/) (Samuel Gregory) | AI-assisted engineering keeps humans in control; vibe coding outsources understanding |
| [Andrej Karpathy](https://en.wikipedia.org/wiki/Andrej_Karpathy) (2025) | Coined "vibe coding" — the approach this methodology deliberately avoids |

The core insight: AI makes engineers faster. Structure makes sure that speed builds understanding instead of hiding its absence.
