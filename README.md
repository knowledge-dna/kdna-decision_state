# kdna-decision_state

[![KDNA Spec](https://img.shields.io/badge/KDNA-v1.0--rc-4c1)](https://github.com/knowledge-dna/KDNA)
[![Trust](https://img.shields.io/badge/scope-%40aikdna-blue)](https://github.com/knowledge-dna/kdna-registry)

**Decision state judgment** — classify whether a discussion produced an actionable decision using the four-element commitment test. Not a meeting summarizer.

## Core Insight

A meeting can feel productive while being structurally unproductive. Social agreement ('sounds good') is not a decision state. The four commitment elements — specific choice, named owner, concrete action, deadline — must all be present and verifiable.

## The Four Questions (v2.1 governance)

### 1. Where does it come from?

- **Authored by**: KDNA Team
- **Evidence type**: practice patterns + observed cases across product management, executive decision-making, and team coordination
- **Signed by**: `@aikdna` official trust key (fingerprint `43d22af8f0e1`)

### 2. Where does it apply?

This KDNA helps agents diagnose **decision state** in:

- meeting outcomes, project status updates, async decision threads
- product and strategy reviews where commitments are claimed
- cross-functional handoffs where ownership and timing must be explicit
- any context where "we decided" may mask unresolved discussion

### 3. How is it verified?

- `kdna verify @aikdna/decision_state --judgment` — checks v2.1 governance fields
- `kdna compare @aikdna/decision_state --input "<meeting summary>"` — runs with/without KDNA
- `evals/` directory contains 10 standard eval cases for classification accuracy, false positive rate, missing element identification, and recommendation specificity

### 4. When does it NOT apply?

**Do not load** when:

- the explicit goal is social cohesion rather than operational output (team-building, all-hands updates)
- the context is collective responsibility with pre-defined shared ownership (emergency response, pair programming)
- the user is asking for a narrative summary without decision assessment
- the discussion is intentionally open-ended exploration (early-stage research, creative ideation)

## Known Failure Risks

| Risk | When it shows up |
|------|---|
| Mistaking social agreement for commitment | Cheerful standups with zero action items recorded |
| Treating vague conditional language as decided | "Pending approval" without named approver or criteria |
| Misclassifying conditional as executable | Owner named but lacks authority or resources |
| Over-rigid structural checking | Relationship-building meetings where no decision was the goal |

## Decision State Taxonomy

| State | Definition |
|-------|------------|
| **UNRESOLVED** | One or more of the four commitment elements is missing |
| **CONDITIONAL** | All four elements present but gated by an external condition |
| **INTENTIONAL_DEFERRAL** | All four deferral elements present: what info, by when, who decides, interim action |
| **EXECUTABLE_DECISION** | All four elements present, owner has authority, no blockers |

## Files

| File | Purpose |
|------|---------|
| `KDNA_Core.json` | Axioms (with v2.1 boundaries), ontology, frameworks, causal structure, stances |
| `KDNA_Patterns.json` | Terminology, banned terms, misunderstandings (with v2.1 boundaries), self-checks |
| `KDNA_Scenarios.json` | Scenario signals that should shift strategy |
| `KDNA_Cases.json` | Concrete cases showing classification in practice |
| `KDNA_Reasoning.json` | Reasoning chains: conclusion → logic → so_what |
| `KDNA_Evolution.json` | Capability stages (summarizer → extractor → classifier → validator), measurements |
| `evals/` | 10 standard eval cases for verification |
| `kdna.json` | Domain manifest (name, version, signature, judgment_version) |

## License

CC BY 4.0 — attribution required, derivative judgment frameworks welcome.

---

## Install

```bash
kdna install @aikdna/decision_state
kdna verify @aikdna/decision_state --judgment
```
