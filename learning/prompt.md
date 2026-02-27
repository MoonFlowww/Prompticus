# Learning
 
Prompts for building deep, structured understanding of new concepts from first principles.
 
---
 
## Explain: \<CONCEPT\>
 
**Usage:** Replace `<CONCEPT>` with the concept you want to learn (e.g., `Kalman Filter`, `Cointegration`, `Attention Mechanism`).
 
---
 
```
Explain: <CONCEPT>
 
You will build the explanation in strict sequence. Each step must only use what was established in prior steps. Do not skip ahead.
 
---
 
STEP 1 — NAKED LOGIC
Describe the core operation as if it had no domain.
What is the fundamental action or transformation being performed?
State it in terms of: what goes in, what operation occurs, what comes out.
No domain vocabulary. No implementation. Pure mechanism.
(3–5 sentences max)
 
---
 
STEP 2 — ENVIRONMENT
Now introduce the domain this logic lives in.
What does "input" actually mean here? What does "output" actually mean here?
What constraints does the real-world environment impose on the naked logic?
How does the environment shape or limit the logic from Step 1?
(3–5 sentences max)
 
---
 
STEP 3 — MOVING PARTS
List only the sub-components a practitioner must distinguish to use this correctly.
For each: name it, say what role it plays in the logic (Step 1), and how the environment (Step 2) constrains it.
Do not introduce new concepts not traceable to Steps 1–2.
(1 sentence per component, 3–6 components)
 
---
 
STEP 4 — RECREATION TEST
Describe what someone needs to hold in their head to reconstruct this concept from scratch.
If it is code-adjacent: give a minimal pseudocode or structural sketch (≤10 lines).
If it is not: give a minimal analogy that preserves the logic exactly, not just the feel.
 
---
STEP 5 — CONCEPT LANDSCAPE
You will map where this concept sits relative to others. Three sub-parts:
 
5a — SAME LOGIC, DIFFERENT ENVIRONMENT
Name 1–2 concepts that share the naked logic from Step 1 but operate in a different domain.
For each: state what differs in the environment and what that changes in practice.
 
5b — SAME ENVIRONMENT, STRONGER/WEAKER LOGIC
Name 1–2 concepts from the same domain that solve a similar problem but with a more powerful
or more constrained version of the logic.
For each: state exactly what capability you gain or lose, and when that tradeoff matters.
 
5c — WHEN THIS CONCEPT STOPS BEING THE RIGHT TOOL
Describe the condition (scale, constraint, data type, regime) under which you would
reach for a concept from 5b instead of this one.
One concrete triggering scenario.
 
Do not list concepts for completeness. Only include a concept if the contrast
reveals something about the structure of the current one.
---
 
HARD RULES
- No intro sentences. Start each step immediately.
- No history, no motivation, no "this is important because."
- No jargon without a definition embedded in the same sentence (≤8 words).
- If Steps 1 and 2 feel identical for this concept, explicitly state why in Step 2 instead of repeating.
- If you are uncertain about any claim, prefix it with "Uncertain:"
```
