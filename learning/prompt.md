# Learning
 
Prompts for building deep, structured understanding of new concepts from first principles.
 
---

 ```markdown
# CONCEPT EXPLANATION PROTOCOL
## Input
**Concept to explain:** <CONCEPT>

---

## Instructions
Build the explanation in strict sequence. Each step must only use what was established in prior steps.
Do not skip ahead. Do not merge steps.

---

## STEP 1 — NAKED LOGIC

Describe the core operation as if it had no domain.

- What is the fundamental action or transformation being performed?
- State it in terms of: **what goes in**, **what operation occurs**, **what comes out**
- No domain vocabulary. No implementation. Pure mechanism.

> **Limit:** 3–5 sentences maximum.

---

## STEP 2 — ENVIRONMENT

Introduce the domain this logic lives in. Build strictly from Step 1.

- What does "input" actually mean here?
- What does "output" actually mean here?
- What constraints does the real-world environment impose on the naked logic?
- How does the environment shape or limit the logic from Step 1?

> **Rule:** If Steps 1 and 2 feel identical for this concept, explicitly state why in Step 2 instead of repeating.

> **Limit:** 3–5 sentences maximum.

---

## STEP 3 — MOVING PARTS

List only the sub-components a practitioner must distinguish to use this correctly.

For each component, provide in one sentence:

| Component | Role in Logic (Step 1) | Environmental Constraint (Step 2) |
|---|---|---|
| `name` | what role it plays | how the environment constrains it |

**Additional rule per component:** State what breaks if you remove it.

> **Rule:** Do not introduce any concept not traceable to Steps 1 or 2.
> **Limit:** 3–6 components maximum.

---

## STEP 4 — FAILURE MODE

Describe the most common way someone correctly understands Step 1 but **misapplies** it due to Step 2's constraints.

- What does correct understanding of the logic look like?
- What does the misapplication look like in practice?
- What is the exact constraint from Step 2 that was violated?

> This step tests whether the logic/environment separation from Steps 1–2 actually holds.

---

## STEP 5 — CONCEPT LANDSCAPE

Map where this concept sits relative to others. Three sub-parts, strictly in order.

### 5a — SAME LOGIC, DIFFERENT ENVIRONMENT
Name 1–2 concepts that share the naked logic from Step 1 but operate in a different domain.

For each: state what differs in the environment and what that changes in practice.

### 5b — SAME ENVIRONMENT, DIFFERENT POWER
Name 1–2 concepts from the same domain that solve a similar problem but with a **more powerful or more constrained** version of the logic.

For each: state exactly what capability you gain or lose, and when that tradeoff matters.

### 5c — BOUNDARY CONDITION
Describe the condition (scale, constraint, data type, regime) under which you would reach for a concept from 5b instead of this one.
Give one concrete triggering scenario.

> **Rule:** Do not list concepts for completeness. Only include a concept if the contrast reveals something about the structure of the current one.

---

## STEP 6 — RECREATION TEST

Describe what someone needs to hold in their head to reconstruct this concept from scratch.

**If code-adjacent:**
Provide a minimal pseudocode or structural sketch.
```
[≤10 lines]
```

**If not code-adjacent:**
Provide a minimal analogy that preserves the logic exactly — not just the feel.
The analogy must map cleanly onto Step 1, not Step 2.

**Then identify:**
One concept the reader definitely knows that shares the same naked logic (Step 1) but lives in a different environment (Step 2).
This anchors the analogy structurally, not decoratively.

---

## STEP 7 — SELF-AUDIT

Answer the following checks before finalizing the response. Verdict: `PASS` / `FAIL` + one sentence.

| Check | Question | Verdict |
|---|---|---|
| **Logic purity** | Does Step 1 contain any word that only makes sense inside the domain from Step 2? | |
| **Environment separation** | Does Step 2 introduce any new operation not present in Step 1? | |
| **Component necessity** | Does every component in Step 3 have a stated consequence if removed? | |
| **Analogy fidelity** | Does the analogy in Step 6 map onto Step 1 without importing domain vocabulary from Step 2? | |

> **Rule:** If any check is `FAIL`, rewrite the relevant step before outputting the final response.

---

## HARD RULES

- **No intro sentences.** Start each step immediately.
- **No history, no motivation**, no "this is important because."
- **No jargon** without a definition embedded in the same sentence (≤8 words).
- If you are uncertain about any claim, prefix it with `Uncertain:`
- The concept type must be declared before Step 1:
  - `PROCEDURAL` — a thing that does
  - `STRUCTURAL` — a thing that is
  - `RELATIONAL` — a thing that connects
  
  The declared type governs how Step 1 is framed. If the concept does not fit cleanly, state which type dominates and why.
```
