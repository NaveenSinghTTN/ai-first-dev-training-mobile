# Prompt Strategy Document
### Phase 1 Deliverable — AI-First Development Training Program

**Developer name:** [Your name]
**Feature chosen:** [Option A — Notifications Center / Option B — Activity Feed with Filters]
**Date submitted:** [Date]

---

> **How to use this template**
> Fill in each section with your actual thinking. Do not pad.
> The sections with the most weight in assessment are 2, 3, and 5.
> A good submission is 500–800 words. Quality over length.

---

## 1. Feature Breakdown

*Split the feature into at least 6 discrete AI tasks. Each should be small enough for a single Composer/Agent prompt. Order them as you would actually build them — think about dependencies.*

| # | Task | Why this order? |
|---|---|---|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |

---

## 2. Full Prompt — Task [X]

*Write the complete CDIR prompt for one of your tasks above. Be specific — reference file paths, existing components, and patterns even if hypothetical.*

**Which task:** Task [number] — [task name]

**Context** *(what does AI need to know upfront?)*
```
[What project, what stack, what existing patterns, what constraints]
```

**Decomposition** *(how did you break this task down before writing the prompt?)*
```
[The thinking you did before writing — what did you decide NOT to include?]
```

**The full prompt:**
```
[Write the complete prompt here exactly as you would type it into Cursor]
```

---

## 3. Full Prompt — Task [Y]

*Write a second complete CDIR prompt for a different task.*

**Which task:** Task [number] — [task name]

**Context:**
```
[What does AI need to know?]
```

**Decomposition:**
```
[How did you break this down?]
```

**The full prompt:**
```
[Write the complete prompt here]
```

---

## 4. Plan Mode Outline

*Choose the most complex task in your breakdown. Write what you would expect the Agent to produce in Plan Mode before it writes any code.*

**Which task:** Task [number] — [task name]

**Questions the agent should ask before starting:**
- [Question 1]
- [Question 2]

**Files the agent should reference:**
- [File path and why]
- [File path and why]

**Steps the plan should contain:**
1. [Step]
2. [Step]
3. [Step]

**What should the agent NOT do in this task?**
- [Constraint 1]
- [Constraint 2]

---

## 5. `.cursor/rules` Additions

*List at least 3 rules you would add specifically for this feature. Explain the reasoning behind each.*

**Rule 1:**
```
[The rule text]
```
*Why:* [Explain what mistake this prevents or what behaviour it enforces]

**Rule 2:**
```
[The rule text]
```
*Why:* [Explain the reasoning]

**Rule 3:**
```
[The rule text]
```
*Why:* [Explain the reasoning]

---

## 6. AI Failure Anticipation

*Identify 2 things you expect AI to get wrong or hallucinate for this feature.*

**Failure 1:**

*What AI will likely get wrong:*
[Describe the specific failure — not "bad code" but what precise mistake]

*How you would catch it in review:*
[What would you look for in the diff?]

*Follow-up prompt to correct it:*
```
[Write the actual follow-up prompt you would use]
```

---

**Failure 2:**

*What AI will likely get wrong:*
[Describe the failure]

*How you would catch it in review:*
[What to look for]

*Follow-up prompt to correct it:*
```
[The corrective prompt]
```

---

## 7. One Thing I Learned

*One concrete thing from the reading, video, or exercises that surprised you or changed how you think about AI-assisted development. Be specific — don't summarise the material, show how it changed your thinking.*

[Your answer here]

---

*Phase 1 Prompt Strategy Document — v1.0*
