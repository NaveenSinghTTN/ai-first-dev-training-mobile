# Phase 1: AI-First Development with Cursor
### Developer Briefing - AI-First Training Program

---

## Before You Begin

Read this document fully before opening Cursor. The instinct to jump straight into the tool is exactly the habit this program is designed to break.

---

## Part 1 - The Mindset Shift

### Your job is not to write code anymore

Here is the most important idea in this entire program, from Greg Detre's *A Field Guide to AI-First Development*:

> *"Let go emotionally of the idea that you are there to write code. Your job (as developer) is to be a manager of an AI team of developers."*

There is an old joke: in the future, all factories will have two employees - a person and a dog. The person is there to feed the dog, and the dog is there to bite the person if they try to touch the machines.

AI-first development works the same way. The temptation to jump in and fix a function yourself, to tweak a style manually, to just write that one component by hand - resist it. That is the old reflex. Your new job is:

- **Deciding** what to build and in what order
- **Directing** AI with precise, well-structured instructions
- **Reviewing** output critically - not accepting it, reviewing it
- **Recovering** from bad output with better follow-up prompts
- **Fixing inputs, not outputs** - when AI makes the same mistake twice, that is a signal to improve your rules or your prompt, not to fix the code by hand

This is a different skill set. It takes deliberate practice. That is what Phase 1 is for.

### What AI-first is not

- It is not typing less. It is thinking differently.
- It is not autocomplete on steroids. It is directing a capable but literal collaborator.
- It is not about trusting AI output. It is about knowing exactly when to trust it and when not to.
- It is not about moving faster by cutting corners. It is about spending your energy on judgment rather than implementation.

### The three failure modes to avoid from day one

**Failure mode 1: Accepting output without reading it**
AI-generated code can look right while being subtly wrong. The faster AI works, the more important your review becomes. Read every diff. Catch every deviation from your intended architecture before it compounds.

**Failure mode 2: Asking for everything at once**
"Build me a notifications screen" is not a prompt - it is a wish. Good AI-first development means decomposing problems into small, specific, bounded tasks. The quality of your output is directly proportional to the quality of your decomposition.

**Failure mode 3: Fixing AI mistakes by hand**
When the output is wrong, the reflex is to fix it directly. Resist this. Fix the prompt instead, or update your rules file. You are building a factory. Fix the factory, not the product it made.

> **One thing to set expectations on:** Reviewing AI-generated code feels slow at first - slower than just writing it yourself. That is normal. You are building a new instinct. By Phase 2 it will feel natural.

---

## Part 2 - Watch This First

**Before doing anything in Cursor, watch this video in full:**

### Primary Video (Required)
**[Cursor for Beginners - Full Walkthrough](https://www.youtube.com/watch?v=2aldTxnbNt0)**
Watch this first. It covers the interface, core features, and basic workflows. ~45 minutes. Do not skip.

### Supplementary Video (Optional)
**[Best Cursor Workflow That No One Talks About](https://www.youtube.com/watch?v=2PjmPU07KNs)**
Watch the first 18 minutes if time allows. Covers PRD-driven development - writing a planning document before prompting. Some developers found this video harder to follow; feel free to skip if the primary video covered enough.

---

## Part 3 - Read These

### Required (do these before the exercises)

#### 1. Cursor Official Docs - Quick Start
**[cursor.com/docs](https://cursor.com/docs)**
Skim the Quickstart, Agent, and Context sections. ~20 minutes. Goal: understand the vocabulary (Tab, Chat, Composer, Agent, Rules, `@` references) before you start using them.

#### 2. Best Practices for Coding with Agents - Cursor Blog ⭐ Most Important
**[cursor.com/blog/agent-best-practices](https://cursor.com/blog/agent-best-practices)**
This is the single most important document in your reading list. Read it fully. Key things to internalise:

- **Start with plans.** Use Plan Mode (`Shift+Tab` in agent input) before coding. The agent researches your codebase, asks clarifying questions, and creates a reviewable plan before writing a line of code. For complex tasks, this is not optional - it is how experienced developers work with AI.
- **Manage context deliberately.** Do not tag every file. Let the agent find context through `@codebase` search. Include only what is relevant. Long, noisy conversations make agents dumber.
- **Know when to start a new conversation.** If the agent seems confused, keeps repeating mistakes, or you are moving to a different feature - start fresh. Use `@Past Chats` to pull in previous context selectively.
- **Rules are always-on context.** Your `.cursor/rules` file is read at the start of every conversation. It is the most important thing you configure in your project.
- **Review AI output actively.** Use the diff view. Click Stop if the agent goes the wrong direction. Use Agent Review after completion. Do not let bad output accumulate.

### Recommended (read after completing the checklist if time allows)

#### 3. Cursor Rules Documentation
**[cursor.com/docs/rules](https://cursor.com/docs/rules)**
Understand the four rule types: Always, Auto Attached, Agent Requested, and Manual. Useful context before the `.cursor/rules` exercise in Part 6.

#### 4. How to Write Great Cursor Rules - Trigger.dev
**[trigger.dev/blog/cursor-rules](https://trigger.dev/blog/cursor-rules)**
Ten practical tips for writing effective rules files.

#### 5. A Field Guide to AI-First Development
**[makingdatamistakes.com/ai-first-development](https://www.makingdatamistakes.com/ai-first-development/)**
Long read (~22 minutes) written by someone who built a 60,000-line production codebase without writing a single line of code by hand. Worth it when you have the time.

---

## Part 4 - The Cursor Skill Checklist

### Core (complete before the deliverable)

These four items are the foundation. Each takes 20–40 minutes. Do them in order.

| # | Skill | Task to Complete | ✓ |
|---|---|---|---|
| 1 | **Plan Mode (`Shift+Tab`)** | Open Agent input. Toggle Plan Mode. Give a non-trivial task - e.g. "Add an endpoint that returns a paginated list of notifications with filters". Read the plan it produces. Edit one step. Approve it. Observe the difference vs jumping straight to code. | ☐ |
| 2 | **Composer / Agent (`Cmd+I`)** | Ask Composer to create a new component or module from a description only - a UI component, an API endpoint, a background job, whatever fits your stack. Review the output carefully before accepting. Reject at least one suggestion and ask for a revision. | ☐ |
| 3 | **`@codebase` and `@file`** | First: ask "Where is authentication handled in this project?" without tagging any file. Then: ask Cursor to create a new module that follows the same pattern as an existing one, referencing it with `@file`. Compare the quality of both outputs. | ☐ |
| 4 | **`.cursor/rules`** | Create a rules file for your project. Follow the exercise in Part 6. This checklist item and Part 6 are the same task. | ☐ |

### Extended (complete during Phase 2 - not required before the deliverable)

You will naturally cover these while building the Phase 2 project. No need to force them now.

| # | Skill | When You'll Use It |
|---|---|---|
| 5 | **Tab Completion** | Throughout Phase 2 |
| 6 | **Inline Edit (`Cmd+K`)** | Refactoring existing code |
| 7 | **Chat (`Cmd+L`)** | Exploring an unfamiliar codebase |
| 8 | **`@docs` reference** | When working with framework APIs (React, Next.js, Express, FastAPI, etc.) |
| 9 | **Multi-file edits** | Updating shared utilities across modules |
| 10 | **Prompt iteration** | Every time AI gives you bad output |
| 11 | **New conversation discipline** | When switching between features |
| 12 | **Agent Review** | After every significant generation |

---

## Part 5 - The CDIR Prompt Framework

This is the mental model to use for every AI task, big or small.

```
C - Context     What does AI need to know?
                (file structure, existing patterns, tech stack, constraints)

D - Decompose   Can I break this into smaller steps?
                (do not ask for everything at once)

I - Instruct    Be specific: format, style, edge cases, what NOT to do

R - Review      Read the output critically.
                What is wrong? What needs a follow-up?
```

The R step is as important as the others. AI code can look correct and be subtly wrong. Read every diff. Catch architectural deviations before they compound.

### Seeing CDIR in Practice

The two examples below are deliberately full-stack - one leans frontend, one leans backend - so you can see the same framework applied on both sides of the wire. Map the specifics to whatever stack you work in.

**Example 1 - Notifications feature (frontend-leaning, full-stack)**

❌ **Weak prompt:**
> "Build a notifications system"

✅ **Strong prompt:**
> "In our app, build a `NotificationsPanel` component that renders a dropdown list of notifications with an unread count badge. It should:
> - Consume `GET /api/notifications` via our existing query hook pattern (@file src/hooks/useQuery.ts) - do not add a new data-fetching library.
> - Use our existing `Panel` layout component (@file src/components/Panel.tsx) as the shell.
> - Support optimistic mark-as-read: on click, update local state immediately, then call `PATCH /api/notifications/:id/read`. On failure, revert and surface the error via our existing `toast` util (@file src/utils/toast.ts).
> - Show an empty state when there are no notifications.
> - Out of scope: real-time delivery (polling/WebSocket will be added in a follow-up task), notification preferences UI.
>
> Follow the component structure in @file src/components/InboxPanel.tsx as your reference. Mock the API response with 5 items for now - the endpoint itself is a separate task."

---

**Example 2 - Audit log / activity feed (backend-leaning, full-stack)**

❌ **Weak prompt:**
> "Add an audit log"

✅ **Strong prompt:**
> "Add a `GET /api/audit-log` endpoint to our backend that returns paginated audit events filtered by `userId`, `action`, and a `from`/`to` date range. Requirements:
> - Follow the route/controller/service split used in @file server/routes/users.ts.
> - Use the auth middleware in @file server/middleware/auth.ts - only admins can query across all users; regular users can only query their own events.
> - Use our existing pagination helper (@file server/utils/pagination.ts). Default page size 25, max 100.
> - The underlying `audit_events` table already exists - do not create a new migration. Schema is in @file server/db/schema/audit.ts.
> - Validate query params with our existing Zod pattern (@file server/validators/common.ts). Return 400 on invalid input.
> - Out of scope: the frontend `AuditLogView` component (separate task), writing new audit events (already handled by existing middleware).
>
> No new libraries. Match the error-handling conventions in @file server/routes/users.ts exactly."

---

The difference: the strong prompts give AI a **bounded space** to work in. It knows what exists, what to reuse, what not to touch, and where the edges are. Notice how each prompt explicitly calls out what is **out of scope** - that constraint is often more important than what is in scope, because it stops AI from quietly expanding the change.

### Plan before you prompt

From the Cursor blog: *"The most impactful change you can make is planning before coding."*

For any task that takes more than one prompt:
1. Write a brief planning note - or use Plan Mode as your first message to the agent
2. Break the feature into discrete steps
3. Get the agent to produce and review a plan before it writes code
4. Execute step by step, reviewing after each

This is not bureaucracy. It is the habit that separates developers who use AI well from those who use it as a faster way to make a mess.

---

## Part 6 - The `.cursor/rules` Exercise

Creating a rules file forces you to articulate things you usually just know - which is exactly the skill AI-first development demands. The rules file is permanent context. It is the most important thing you configure in your project.

### Starter Rules

Here are 5 rules to get you started. They are deliberately stack-agnostic - translate each one to your world (TypeScript, Python, Go, Ruby, whatever). Your job is to understand why each rule exists, then add at least 5 more specific to your project.

```
1. Always use strict type checking (TypeScript strict mode, Python type hints,
   Go's standard typing, etc.). Never use `any`, untyped dictionaries, or
   silent fallbacks in new code.

2. All data fetching goes through a shared client/service layer - no inline
   fetch/axios/requests calls in UI components, route handlers, or view
   logic.

3. All styling/theming values come from a central tokens file (e.g.,
   `theme/colors.ts`, `_variables.scss`, a tailwind config). No hardcoded
   hex values, magic pixel sizes, or inline styles in new code.

4. Never install a new package, add a new dependency, or introduce a new
   framework without explicitly asking me first.

5. Follow the existing patterns in [reference file for your stack] as the
   template for new code in the same category - components, endpoints,
   migrations, background jobs, etc.
```

Now add at least 5 more based on your own project conventions - think through:

**Project structure**
- Where do feature modules live? Shared utilities? Tests?
- What is the naming convention for files, folders, classes, and functions?

**Patterns and architecture**
- How are API calls handled? (Direct fetch? Shared client? Service layer? Repository pattern?)
- What state / data management approach is used? (Redux, Zustand, server state libraries, a DB ORM, etc.)
- How is routing / request handling organised?

**Styling or presentation conventions**
- Tokens, CSS modules, styled components, utility classes, template conventions
- How is spacing / layout managed?
- Formatting and linting conventions

**Type safety and validation**
- Boundary validation (Zod, Pydantic, JSON schema, etc.) - where is it required?
- How are errors modelled and returned?

**What AI must never do without asking**
- Change routing / navigation structure
- Modify database schema / migrations
- Touch auth or security-sensitive modules
- Modify files outside the current task scope

**Error handling and observability**
- How are errors logged? What goes to Sentry / your logger?
- How are loading, empty, and error states handled in the UI?

### Reference

Browse community examples at [cursor.directory/plugins](https://cursor.directory/plugins) - pick the plugin closest to your stack (React, Next.js, Python, Rails, etc.) and read a few rules files to calibrate your thinking. Do not copy wholesale - the point is to see the level of specificity that works.

> *"Add rules only when you notice the agent making the same mistake repeatedly. Don't over-optimise before you understand your patterns."* - Cursor blog

Start with 10 solid rules. You will add more during Phase 2 as the project reveals your patterns.

---

## Part 7 - The Phase 1 Deliverable

Submit a **Prompt Strategy Document** for one of the two features below. Choose the one that interests you more.

A starter template is available at [`phase-1/prompt-strategy-template.md`](./prompt-strategy-template.md). Use it to structure your document - fill in your thinking, don't fill in the blanks mechanically.

---

**Option A - "Notifications Center"**
A signed-in user sees a notifications panel with an unread-count badge, can mark notifications read individually or all at once, filters by type (e.g. mentions, system, activity), and receives new notifications without a full page refresh (polling or WebSocket - your choice).
*Covers:* UI state management, API design, real-time delivery, optimistic updates, read/unread state.

**Option B - "Activity Feed with Filters"**
A user views a paginated activity feed showing recent events (posts, comments, logins, status changes, etc.), filters by event type / date range / actor, and opens an event detail view.
*Covers:* query design, pagination strategy, filter state, empty and loading states, authorization rules on who can see what.

> Both features are intentionally broad - pick whichever interests you more. You are free to emphasise the layer that matches your day job (frontend, backend, or full-stack) as long as your prompts cover the **full surface area** of the feature: data model, API, UI, error handling.

---

### What your document must contain

**1. Feature Breakdown**
Split the feature into at least 6 discrete AI tasks. Each task should be small enough that a single Composer/Agent prompt could handle it. Order them as you would actually build them.

**2. Two Full Prompts (CDIR)**
Write the complete prompt you would use for 2 of those 6 tasks. Be specific. Reference file paths, components, and patterns - even if they are hypothetical. Show your context, decomposition, and instructions.

**3. Plan Mode Outline**
For the most complex task in your breakdown, write what you would expect the Agent to produce in Plan Mode before coding. What questions should it ask? What files should it reference? What steps should the plan contain?

**4. `.cursor/rules` Additions**
List at least 3 rules you would add to your rules file specifically for this feature. Explain the reasoning behind each one.

**5. AI Failure Anticipation**
Identify 2 things you expect AI to get wrong or hallucinate for this feature. How would you catch them in your review? How would you correct with a better follow-up prompt?

**6. One thing you learned**
One concrete thing from the reading, video, or exercises that surprised you or changed how you think about AI-assisted development.

### Format and length

Submit as a Markdown document. Length should reflect quality, not padding. 500–800 words is typical for a good submission. Do not pad. Do not summarise the reading at me - show your own thinking applied to the feature.

**Submission:** Share in the designated team channel/folder.

---

## Part 8 - How Your Submission Will Be Assessed

You will be scored across four dimensions, each out of 5. **Total: 20 points. 16+ clears Phase 1.**

| Dimension | What We Are Looking For | Score |
|---|---|---|
| **Decomposition quality** | Are the 6 tasks logically ordered? Is each small enough for a single prompt? Does the order reflect real build sequencing? | /5 |
| **Prompt specificity** | Do the CDIR prompts provide enough context for AI to produce usable output? Are they specific about patterns, files, and constraints? | /5 |
| **Failure awareness** | Are the identified failure points realistic? Is the recovery approach prompt-based (not "fix it manually")? | /5 |
| **Clarity of thinking** | Does the document reflect genuine thought about the problem, or just surface compliance? Is the Plan Mode outline credible? | /5 |

---

## Quick Reference - Key Resources

| Resource | Link |
|---|---|
| 🎬 Primary video (required) | [youtube.com/watch?v=2aldTxnbNt0](https://www.youtube.com/watch?v=2aldTxnbNt0) |
| 🎬 PRD workflow video (optional) | [youtube.com/watch?v=2PjmPU07KNs](https://www.youtube.com/watch?v=2PjmPU07KNs) |
| Cursor official docs | [cursor.com/docs](https://cursor.com/docs) |
| Agent best practices | [cursor.com/blog/agent-best-practices](https://cursor.com/blog/agent-best-practices) |
| Cursor rules docs | [cursor.com/docs/rules](https://cursor.com/docs/rules) |
| How to write great cursor rules | [trigger.dev/blog/cursor-rules](https://trigger.dev/blog/cursor-rules) |
| AI-first field guide | [makingdatamistakes.com/ai-first-development](https://www.makingdatamistakes.com/ai-first-development/) |
| Cursor community rules (all stacks) | [cursor.directory/plugins](https://cursor.directory/plugins) |
| SpecStory (prompt log extension) | Install from Cursor extensions marketplace |
| Deliverable template | [phase-1/prompt-strategy-template.md](./prompt-strategy-template.md) |

---

*Phase 1 Briefing - AI-First Development Training Program*
*Version 2.0 - Universal (full-stack track)*
