# ROUTING.md — @aikdna/decision_state

## When this domain SHOULD be loaded

- Evaluating whether a meeting or discussion produced a real decision
- Determining if a team has committed to action or is still discussing
- Checking if a proposal is actionable (has owner, deadline, criteria)
- Preventing false actionization (treating discussion as commitment)

## When this domain should NOT be loaded

- The task is to schedule or organize a meeting (logistics, not judgment)
- The task is to take meeting notes or summarize discussion (recording, not judgment)
- The task is purely informational (what was decided, not whether it was a real decision)

## Easily confused tasks (contamination risks)

| Task that looks relevant | Why it should NOT load this domain |
|--------------------------|-----------------------------------|
| "Take notes for our standup" | Recording, not judging |
| "Schedule a meeting for next week" | Logistics, not judgment |
| "What did we decide last sprint?" | Information retrieval |
| "Write a meeting summary" | Summarization, not classification |

## Recommended test statements

**Should load:**
1. "Did our planning meeting actually produce decisions or just discussion?"
2. "Is this proposal ready to execute, or is it still ambiguous?"
3. "The team agreed on the plan — is that a real commitment?"

**Should skip:**
1. "Schedule our weekly review for Tuesday"
2. "Summarize what was discussed in the meeting"
3. "Who was in the meeting yesterday?"

## Confidence guidance

- Load without asking when: task is explicitly about whether something is a decision vs discussion
- Always skip when: task is logistics, recording, or information retrieval
