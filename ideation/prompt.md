# Ideation
 
Prompts to verify and find hypothesis, as well as finding improvement ideas (will stick to the core idea).
 
---
 
## Explain: \<IDEA\>
 
**Usage:** Replace `<IDEA>` with the hypothesis you want to verify/elaborate (e.g., `Analyzing phase transition via Local renormalization group over 3d space`).
 
---


```Markdown
# IDEA STRESS-TEST & IMPROVEMENT PROTOCOL

## Input
**Idea to evaluate:** <IDEA>

---

## Instructions
Proceed in strict sequence. Each step builds on the previous.
Do not merge steps. Do not skip ahead.

---

## STEP 1 — IDEA DISTILLATION

State the idea in its most compressed, unambiguous form.
One sentence: what it claims, assumes, and produces.

Then explicitly separate:

| Component | Description |
|---|---|
| **Claim** | What is asserted |
| **Assumptions** | What is taken for granted, including implicit ones |
| **Problem Solved** | What problem it is meant to solve |

> If you cannot separate these cleanly, state that before continuing.

---

## STEP 2 — FORMAL STRESS-TEST

Test the claim from Step 1 against hard constraints.

**For each check, provide:**
- **Verdict:** `PASS` / `FAIL` / `UNCERTAIN`
- **Justification:** one sentence

### 2a — THEOREM COMPLIANCE
Does the idea violate any known result, theorem, or proven bound in its domain?
If it operates near a known limit (computational complexity, statistical identifiability, logical undecidability), state which and whether the idea respects it.

### 2b — ASSUMPTION AUDIT
List every assumption embedded in the idea, including implicit ones.

For each assumption, classify it:
- `ALWAYS TRUE`
- `SOMETIMES TRUE`
- `UNVERIFIABLE`

Flag any assumption doing **heavy load** — i.e., the idea collapses if it is removed.

### 2c — EXCEPTION MAP
Describe the conditions under which the idea fails, breaks, or produces wrong output.
How many distinct sub-cases or parameter regimes does it require to stay valid?

> More sub-cases = weaker generality. **State the count explicitly.**

### 2d — PROBLEM FIT
Does the idea actually solve the problem stated in Step 1, or does it solve a simpler or adjacent version of it?
State the gap, if any.

---

## STEP 3 — FAILURE DIAGNOSIS

Identify the **single most critical weakness** from Step 2.

- Not a list — **one root cause**
- State which check it came from (`2a` / `2b` / `2c` / `2d`)
- State why it is the most load-bearing failure
- If multiple failures exist, state whether they are **independent** or whether fixing one would resolve others

---

## STEP 4 — IMPROVEMENTS

Propose improvements **strictly ordered by priority**.

For each improvement, fill the following structure:

**Fixes:** `[reference Step 2 check label]`
**Mechanism:** one sentence describing how it fixes the issue

Then evaluate against all five criteria:

| Criterion | Definition | Verdict |
|---|---|---|
| **ASSUMPTION-FREE** | Does the fix introduce new assumptions? | `YES` / `PARTIAL` / `NO` |
| **NON-OVERCOMPLICATED** | Does it increase the parameter or sub-case count from Step 2c? | `YES` / `PARTIAL` / `NO` |
| **AGNOSTIC** | Does it work across the relevant domain without domain-specific tuning? | `YES` / `PARTIAL` / `NO` |
| **STABLE & ROBUST** | Does it degrade gracefully under noise, edge cases, or scale changes? | `YES` / `PARTIAL` / `NO` |
| **OBSERVABLE** | Can its effect be measured or verified directly? | `YES` / `PARTIAL` / `NO` |

> **Rule:** Do not propose improvements that score `NO` on more than one criterion.

---

## STEP 5 — HARDENED RESTATEMENT

Rewrite the original idea incorporating accepted improvements from Step 4.
Use the **same structure as Step 1** (Claim / Assumptions / Problem Solved).

Then complete the following:

| | |
|---|---|
| **Removed** | What was stripped out |
| **Changed** | What was restructured or reframed |
| **Unresolved** | What remains a known weakness |

> **Rule:** The hardened restatement must be strictly simpler or equally simple as Step 1.
> If it is more complex, **flag it explicitly.**

---

## HARD RULES

- **No encouragement.** Do not say the idea is good, promising, or interesting.
- **No new concepts** introduced after Step 1 unless directly required by a failure found in Step 2.
- If a stress-test cannot be performed due to missing information, write `Untestable: [reason]` rather than skipping or guessing.
- Prefer finding **one deep flaw** over listing many surface ones.
- The hardened restatement in Step 5 must be **strictly simpler or equally simple** as Step 1. If it is more complex, flag it.
```
