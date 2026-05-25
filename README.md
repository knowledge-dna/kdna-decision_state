> 🧬 [aikdna.com](https://aikdna.com) — Official website

# @aikdna/decision_state

[![KDNA Spec](https://img.shields.io/badge/KDNA-v1.0--rc-4c1)](https://github.com/aikdna/KDNA)
[![Trust](https://img.shields.io/badge/scope-%40aikdna-blue)](https://github.com/aikdna/kdna-registry)

**Decision state judgment** — classify whether a discussion produced an actionable decision using the four-element commitment test.

## What this KDNA changes

**Before loading this KDNA, an agent tends to:**
- Summarize meeting discussions as if they produced decisions
- Treat social agreement ("sounds good") as commitment
- List action items without checking for owners or deadlines

**After loading this KDNA, an agent will judge:**
- Does this discussion contain all four commitment elements?
- Is "we decided" masking unresolved discussion?
- Which state is this: unresolved, conditional, deferred, or executable?
- Is the owner named and authorized?

## This KDNA is for

- Meeting outcomes, project status updates, async decision threads
- Product and strategy reviews where commitments are claimed
- Cross-functional handoffs where ownership and timing must be explicit
- Any context where "we decided" may mask unresolved discussion

## This KDNA is not for

- Social cohesion contexts (team-building, all-hands updates)
- Collective responsibility with shared ownership (emergency response)
- Narrative summaries without decision assessment
- Intentionally open-ended exploration (early-stage research, ideation)

## Core judgment

A meeting can feel productive while being structurally unproductive. Social agreement is not a decision state. The four commitment elements — specific choice, named owner, concrete action, deadline — must all be present and verifiable.

## Top axioms

1. **Discussion is not decision** — broad agreement is not commitment (`ax-discussion-not-decision`)
2. **Absence of objection is not commitment** — silence is not consent (`ax-absence-not-commitment`)

## Common wrong assumptions

| Wrong assumption | Reality |
|---|---|
| Social agreement = commitment | Productivity is measured by operational output, not sentiment |
| Action items listed = decisions made | Action items without owners/deadlines are a to-do list |
| "We need more data" = valid deferral | Deferral is only valid when structured: what data, by when, who decides |

## Decision state taxonomy

| State | Definition |
|-------|------------|
| **UNRESOLVED** | One or more of the four commitment elements is missing |
| **CONDITIONAL** | All four elements present but gated by an external condition |
| **INTENTIONAL_DEFERRAL** | All four deferral elements present: what info, by when, who decides, interim action |
| **EXECUTABLE_DECISION** | All four elements present, owner has authority, no blockers |

## Known failure risks

| Risk | When it shows up |
|------|---|
| Mistaking social agreement for commitment | Cheerful standups with zero action items |
| Treating vague conditional language as decided | "Pending approval" without named approver or criteria |
| Misclassifying conditional as executable | Owner named but lacks authority or resources |
| Over-rigid structural checking | Relationship-building meetings where no decision was the goal |

## Self-checks

- Are all four commitment elements present (choice, owner, action, deadline)?
- Is the absence of objection being treated as the presence of commitment?
- Is "we decided" a social sentiment or a verifiable commitment?
- Is a named owner present and authorized?

## Example: without KDNA / with KDNA

```
Input: "Team discussed shipping beta next Friday. Alex said payment flow still has bugs. Mia suggested delaying one week. No one objected. Marketing still preparing for Monday launch. No owner named."

Without KDNA:
  → Summarizes the discussion. Lists the beta date, bug report, delay suggestion, and marketing plans.

With @aikdna/decision_state:
  → Classifies as UNRESOLVED. No decision formed. No explicit choice confirmed. No owner named. Blocker (payment bug) unresolved. Marketing date conflicts with product state. Owner must be designated to resolve the release date.
```

## Install

```bash
kdna install @aikdna/decision_state
kdna verify @aikdna/decision_state --judgment
kdna compare @aikdna/decision_state --input "<meeting summary>"
```

## Files

- `KDNA_Core.json` — Axioms, ontology, frameworks, causal structure, stances
- `KDNA_Patterns.json` — Terminology, banned terms, misunderstandings, self-checks
- `KDNA_Scenarios.json` — Scenario signals that shift strategy
- `KDNA_Cases.json` — Concrete cases showing classification in practice
- `KDNA_Reasoning.json` — Reasoning chains: conclusion → logic → action
- `KDNA_Evolution.json` — Capability stages, measurable indicators, growth paths
- `evals/` — 10 standardized eval cases
- `kdna.json` — Domain manifest

## License

CC BY 4.0 — attribution required, derivative judgment frameworks welcome.
