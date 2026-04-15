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
| 1 | **Plan Mode (`Shift+Tab`)** | Open Agent input. Toggle Plan Mode. Give a non-trivial task - e.g. "Create a screen that shows a list of movies with search". Read the plan it produces. Edit one step. Approve it. Observe the difference vs jumping straight to code. | ☐ |
| 2 | **Composer / Agent (`Cmd+I`)** | Ask Composer to create a new React Native screen component from a description only. Review the output carefully before accepting. Reject at least one suggestion and ask for a revision. | ☐ |
| 3 | **`@codebase` and `@file`** | First: ask "Where is navigation handled in this project?" without tagging any file. Then: ask Cursor to create a new component that follows the same pattern as an existing one, referencing it with `@file`. Compare the quality of both outputs. | ☐ |
| 4 | **`.cursor/rules`** | Create a rules file for a React Native project. Follow the exercise in Part 6. This checklist item and Part 6 are the same task. | ☐ |

### Extended (complete during Phase 2 - not required before the deliverable)

You will naturally cover these while building StreamList. No need to force them now.

| # | Skill | When You'll Use It |
|---|---|---|
| 5 | **Tab Completion** | Throughout Phase 2 |
| 6 | **Inline Edit (`Cmd+K`)** | Refactoring existing components |
| 7 | **Chat (`Cmd+L`)** | Exploring an unfamiliar codebase |
| 8 | **`@docs` reference** | When working with React Native APIs |
| 9 | **Multi-file edits** | Updating shared components |
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

**Example domain: OTT App**

❌ **Weak prompt:**
> "Build me a Continue Watching screen"

✅ **Strong prompt:**
> "In our React Native project using our existing NavigationStack pattern (@file src/navigation/MainStack.tsx), create a `ContinueWatchingScreen` component. It should display a horizontal FlatList of content cards showing a thumbnail, title, and a progress bar indicating percentage watched. Use our existing `ContentCard` component (@file src/components/ContentCard.tsx) and `ProgressBar` component. Data comes from a `useContinueWatching` hook I will wire up separately - use a mock array of 5 items for now. No new libraries. Follow the screen structure in @file src/screens/HomeScreen.tsx as your reference pattern."

---

**Example domain: E-commerce App**

❌ **Weak prompt:**
> "Make a product detail page"

✅ **Strong prompt:**
> "In our React Native project, create a `ProductDetailScreen` component. It should include: a scrollable image gallery using our existing `ImageCarousel` component (@file src/components/ImageCarousel.tsx), product name and price (with strikethrough for original price when discounted), a horizontal chip list for size selection, an Add to Cart button pinned to the bottom using our `StickyFooter` pattern (@file src/components/StickyFooter.tsx), and a collapsible product description section. Use mock data. No new libraries. Follow the screen structure in @file src/screens/OrderSummaryScreen.tsx as your reference."

---

The difference: the strong prompts give AI a **bounded space** to work in. It knows what exists, what to reuse, what not to touch, and where the edges are.

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

Here are 5 rules to get you started on a React Native project. Your job is to understand why each one exists, then add at least 5 more of your own.

```
1. Always use TypeScript strict mode. Never use `any` type.

2. All screens fetch data through a custom hook - no inline useEffect + fetch
   in screen components.

3. All colours come from `src/theme/colors.ts` - no hardcoded hex values
   in component files.

4. Never install a new package without explicitly asking me first.

5. Follow the existing screen structure in `src/screens/HomeScreen.tsx`
   as the reference pattern for all new screens.
```

Now add at least 5 more based on your own project conventions - think through:

**Project structure**
- Where do screens live? Components? Hooks? Utilities?
- What is the naming convention for files and folders?

**Patterns and architecture**
- How are API calls handled? (Direct fetch? Custom hook? Centralised client?)
- What state management approach is used?
- What navigation pattern does the project follow?

**Styling**
- StyleSheet.create only? Styled components? NativeWind?
- How is spacing managed?

**What AI must never do without asking**
- Change navigation structure
- Modify files outside the current task scope

**Code quality**
- Error handling conventions
- How are loading and error states handled?

### Reference

Look at community examples at [cursor.directory/plugins/react-native](https://cursor.directory/plugins/react-native) to calibrate your thinking - not to copy from.

> *"Add rules only when you notice the agent making the same mistake repeatedly. Don't over-optimise before you understand your patterns."* - Cursor blog

Start with 10 solid rules. You will add more during Phase 2 as the project reveals your patterns.

---

## Part 7 - The Phase 1 Deliverable

Submit a **Prompt Strategy Document** for one of the two features below. Choose the one that interests you more.

A starter template is available at [`phase-1/prompt-strategy-template.md`](./prompt-strategy-template.md). Use it to structure your document - fill in your thinking, don't fill in the blanks mechanically.

---

**Option A - OTT App: "Watchlist Feature"**
A logged-in user can add and remove titles to their Watchlist, view their full Watchlist on a dedicated screen, and see a Watchlist indicator icon on content cards that are already saved.

**Option B - E-commerce App: "Order Tracking Feature"**
A user can view their active orders, see real-time status updates for each order, and open a detail view showing the full order timeline and list of items.

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
| React Native rules examples | [cursor.directory/plugins/react-native](https://cursor.directory/plugins/react-native) |
| SpecStory (prompt log extension) | Install from Cursor extensions marketplace |
| Deliverable template | [phase-1/prompt-strategy-template.md](./prompt-strategy-template.md) |

---

*Phase 1 Briefing - AI-First Development Training Program*
*Version 1.1 - Updated based on Batch 1 feedback*
