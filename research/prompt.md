# Research
 
Prompts to perform ai-guided researchs, primarily made to find research papers. 
 
---
 
## Explain: \<PROBLEM\>
 
**Usage:** Replace `<PROBLEM>` with the situation your are facing, (e.g., `Creating an 'equitable' correlation measure`), then `<CONSTRAINTS>` (e.g., `Online`, `Parameter-free`, ..) and finally (optional) outputs.

```markdown
# SCIENTIFIC RESEARCH PROTOCOL

## Input
**Problematic:** <PROBLEM>
**Constraints:** <CONSTRAINTS> *(e.g. real-time inference, limited sample size, no ground truth, parameter-free)*
**Goal:** `FIND PAPERS` / `FIND METHODS` / `BOTH`

---

## Instructions
Proceed in strict sequence. Do not merge steps. Do not skip ahead.
Every claim must be traceable to a cited source. No unsourced assertions.

---

## STEP 1 — PROBLEM DECOMPOSITION
Before searching, decompose the problem explicitly.
| Component | Description |
|---|---|
| **Core question** | What is the precise thing being asked or solved? |
| **Domain** | What scientific field(s) does this live in? |
| **Known constraints** | Imported from input — expand if implicit constraints exist |
| **Success criterion** | What does a valid answer or method look like? |

> **Rule:** If the problem is ambiguous, do not proceed. Instead, ask the minimum number of
> clarifying questions needed to remove the ambiguity. Format them as:
>
> **Before proceeding, I need clarification:**
>
> | # | Question | Why it matters |
> |---|---|---|
> | 1 | `[question]` | `[which step it unblocks and how]` |
> | 2 | ... | ... |
>
> Do not ask more than 3 questions. Prioritize questions that affect Step 6 (fit assessment)
> most. Do not proceed until answers are received.

---

## STEP 2 — SEARCH STRATEGY

State the search approach before executing it.

- **Primary keywords** used (list them)
- **Secondary keywords** for adjacent methods or formulations
- **Exclusion terms** — what was deliberately filtered out and why
- **Sources queried** *(e.g. arXiv, PubMed, Semantic Scholar, Google Scholar, IEEE, ACM)*

> **Rule:** If a more precise subfield emerged during search that reframes the problem, state it here and update Step 1 if needed.

---

## STEP 3 — PAPER REGISTRY

List all relevant papers found. For each paper, provide the following:

### Paper Template

**Title:** `[Full title]`
**Authors:** `[Last names, Year]`
**Source:** `[Journal / Conference / Preprint server]`
**Link / DOI:** `[if available]`

| Field | Content |
|---|---|
| **Problem addressed** | One sentence |
| **Method used** | One sentence, mechanism only |
| **Key result** | What was demonstrated or proven |
| **Relevance to current problem** | Why it appears here — direct / adjacent / methodological |
| **Limitation** | What the paper does not cover or assumes |

> **Rule:** Do not include a paper unless its relevance is explicitly stated.
> **Rule:** Minimum 3 papers. If fewer than 3 exist, state `Insufficient literature: [reason]`.

---

## STEP 4 — METHOD EXTRACTION

Extract all distinct methods identified across the papers in Step 3.

For each method:

**Method name:** `[name]`
**Source:** `[cite paper(s) from Step 3]`

| Field | Content |
|---|---|
| **What it does** | Input → operation → output, one sentence |
| **Core mechanism** | The fundamental operation, domain-free if possible |
| **Assumptions** | What must be true for it to work |
| **Failure conditions** | When it breaks or degrades |
| **Complexity / cost** | Computational, statistical, or experimental burden |

> **Rule:** If two methods share the same core mechanism but differ in environment, group them and state the difference explicitly.

---

## STEP 5 — MATHEMATICAL CONTENT

For each key formula or mathematical result encountered:

**Formula:**
$$[equation]$$

| Field | Content |
|---|---|
| **Plain-language meaning** | What this computes, in ≤15 words, no symbols |
| **Each term defined** | Symbol → meaning → unit or type |
| **What it assumes** | Conditions under which it holds |
| **What breaks it** | One condition that invalidates it |
| **Source** | `[cite paper or textbook]` |

> **Rule:** If a formula cannot be vulgarized in ≤15 words without losing its meaning, state `Irreducible: [reason]` and give the closest approximation.
> **Rule:** Do not include formulas that are not directly relevant to the problem in Step 1.

---

## STEP 6 — FIT ASSESSMENT

Evaluate each method from Step 4 against the problem from Step 1.

| Method | Addresses core question | Respects known constraints | Meets success criterion | Verdict |
|---|---|---|---|---|
| `Method A` | `YES / PARTIAL / NO` | `YES / PARTIAL / NO` | `YES / PARTIAL / NO` | `RECOMMENDED / CONDITIONAL / REJECT` |
| `Method B` | ... | ... | ... | ... |

For each `CONDITIONAL` verdict, state the exact condition that must be met.
For each `REJECT` verdict, state the specific mismatch with Step 1.

---

## STEP 7 — SYNTHESIS

Based on Steps 3–6, provide:

**Best method or combination for this problem:** one paragraph, citing sources.

**Remaining gaps:** What does the literature not cover relative to Step 1?

**Suggested next search directions:** 1–3 specific queries or subfields to explore if gaps are critical.

> **Rule:** Do not recommend a method that scored `NO` on any criterion in Step 6.
> **Rule:** Every claim in this synthesis must reference at least one paper from Step 3.

---

## HARD RULES

- **No unsourced claims.** Every factual statement cites a paper from Step 3 or is prefixed with `Prior knowledge:`.
- **No method described without a source.**
- **No jargon** without an inline definition (≤8 words).
- If a paper cannot be verified, write `Unverified:` before citing it.
- If the problem has no existing literature, state `Open problem:` and describe what related work exists at the boundary.
- **No opinions.** Assessments in Step 6 must follow from stated criteria, not judgment.
- Prefer **precision over coverage** — one well-characterized method beats five vague ones.
```
