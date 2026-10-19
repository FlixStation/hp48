# Plan v3 — Slow and incremental

## Goal Description
You want to learn awareness of how software gets built, not become a developer, and you want small goals decided one at a time. So I'm replacing the big multi-sprint plan with two small steps. The full v2.1 plan is **parked** as a reference, not a commitment: [reference_full_plan_v2.1_parked.md](file:///Users/felixloyola/.gemini/antigravity-cli/brain/bddee955-4c0f-42ea-9229-f7d218f7e347/reference_full_plan_v2.1_parked.md)

## What changed from v2.1
| Before | Now |
|---|---|
| Sprints 0 to 5 specified up front | Only the next step is specified |
| Governance files, CI, ADRs, strict typing, property tests from the start | Introduced later, one at a time, when you want them |
| GUI planned for Sprint 2 | **Deferred**, with no date |
| Real engine design first | A throwaway prototype first, to learn and decide |

## Step M0: Product executive summary (no code)
I've drafted a one-page [product_summary.md](file:///Users/felixloyola/.gemini/antigravity-cli/brain/bddee955-4c0f-42ea-9229-f7d218f7e347/product_summary.md). It covers vision, scope, non-goals, principles, roadmap and success criteria.
- **Your action:** read it and tell me what to change.
- **On approval:** I'd save it into the repo as `docs/product-summary.md`. That is the only repo change in M0.

## Step M1: Throwaway prototype (only after M0 is approved)
- **What:** One Python file, about 80 lines, using only the standard library. A terminal RPN calculator with a stack and a few operations: `ENTER`, `+ - * /`, `SWAP`, `DROP`, `DUP`, `CLEAR`.
- **Numbers:** Python's `Decimal` set to 12 digits, so it shows `.3` for `.1 + .2` and `7.` for `7`, as the HP 48 does.
- **Where:** `prototype/rpn.py`. I'd remove the empty `main.py` that `uv init` created.
- **How you'll use it:** `uv run python prototype/rpn.py`, then type `3 ENTER 4 +`.
- **What I'll explain:** In plain language, what the stack is, how each line works, and how to run it.
- **Deliberately not included:** tests, CI, packages, a GUI, and strict HP error messages.
- **Done when:** you run it yourself and can describe what `+` does to the stack.

## After M1
We hold a short review (M2). You decide the next step from a menu, not a schedule. The candidates are tests, version control and CI, more commands, HP-style display, and later the GUI. Each one introduces one concept, such as "what a test is" or "what CI does".

## Verification
- **M0:** you read the summary and approve it.
- **M1:** I run `uv run python prototype/rpn.py` with a scripted input and show you the output. Then you try it yourself.

## Open questions
1. Is the "what it is not" list in the summary right?
2. Do you want short notes or a fuller walkthrough with each step?
