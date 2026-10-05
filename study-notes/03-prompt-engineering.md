# Module 3: Prompt Engineering

← [Back to overview](00-overview.md)

Prompt engineering is the most immediately usable skill in the whole course — it requires no coding and pays off on day one.

## What prompt engineering is and why it matters

**Prompt engineering** is the practice of designing the instructions you give an AI model to reliably get high-quality, relevant output. Because LLMs are extremely sensitive to phrasing, structure, and context, the same underlying request can produce a mediocre result or an excellent one depending purely on how it's asked.

**Practical example:** Asking "Write about our Q3 results" produces a generic, unfocused paragraph. Asking "You are a CFO's chief of staff. Write a 150-word Q3 summary for the board, leading with revenue growth vs. last quarter, then one risk to flag, in a neutral and confident tone" produces something usable with minimal editing.

## Core techniques: zero-shot, few-shot, chain-of-thought, and role prompting

- **Zero-shot prompting:** you ask the model to perform a task with no examples, relying on its general training. *"Classify this customer email as Billing, Technical, or General."*
- **Few-shot prompting:** you give the model 2–5 worked examples of the input→output pattern before your real request, so it mimics the pattern. Useful when tone or format is specific and hard to describe in words.
- **Chain-of-thought prompting:** you ask the model to reason step-by-step before giving a final answer (*"think through this step by step, then give your recommendation"*), which improves accuracy on multi-step reasoning or math-like problems.
- **Role prompting:** you assign the model a persona or expertise frame (*"You are a senior supply-chain analyst..."*), which shifts vocabulary, priorities, and tone toward that role.

**Practical example (few-shot):**
```
Rewrite each customer complaint as a one-line ticket title.

Complaint: "My package never arrived and it's been two weeks!"
Title: Delayed delivery — 2 weeks overdue

Complaint: "The app crashes every time I try to upload a photo."
Title: App crash on photo upload

Complaint: "I was charged twice for the same order."
Title:
```
The two worked examples teach the model the exact title style you want, far more reliably than describing it in prose.

## Crafting prompts for executive tasks: briefings, strategy memos, stakeholder communication

Executive prompts need explicit audience, length, tone, and structure constraints, because executives consume information under time pressure and in a specific format (bullet briefing vs. narrative memo vs. board slide text).

**Practical example:** *"Draft a 5-bullet pre-read for the CEO ahead of a board meeting on our AI pilot. Each bullet ≤ 20 words. Lead with the business outcome, not the technology. Flag one open risk in the final bullet."*

## Crafting prompts for team tasks: documentation, summaries, reports

Team-level prompts are often about consistency and speed at volume: turning meeting transcripts into action items, turning raw notes into structured reports, or standardizing documentation format across a team.

**Practical example:** *"Summarize this meeting transcript into: (1) Decisions made, (2) Action items with owner and due date, (3) Open questions. Use bullet points only."* — applied to every meeting transcript, this produces consistent minutes without manual formatting each time.

## Automating routine workflows with reusable prompt templates

A **prompt template** is a reusable prompt with placeholders you fill in for each new instance, so you don't reinvent the wording every time. This is the bridge between "using AI occasionally" and "AI as part of a standard workflow."

**Practical example:** A recruiting team saves a template: *"Write a rejection email for [CANDIDATE_NAME] who applied for [ROLE]. Warm but concise, invite them to reapply for future roles, do not give detailed feedback."* Every recruiter reuses the same template, swapping in two variables, guaranteeing consistent tone across hundreds of emails.

## Prompt safety and what not to share in public AI tools

Public/consumer AI tools may store or use your inputs (in ways not always suitable for confidential material), and are typically not covered by your company's data-processing agreements. The rule of thumb: never paste customer PII, unreleased financial results, proprietary source code, trade secrets, or legally privileged material into a public consumer AI chat interface — use your organization's approved, contractually-covered enterprise tool instead.

**Practical example:** An employee pastes an unreleased earnings draft into a free public chatbot to "polish the language" — a potential material non-public information (MNPI) leak and a real governance incident, not a hypothetical.

## Hands-on practice: building your personal prompt library

The course encourages participants to keep a running, organized library of prompts that worked well for recurring tasks (with placeholders), rather than rewriting prompts from scratch each time — treating prompt engineering as a reusable skill asset, not a one-off trick.

**Practical example:** A personal library entry might look like:
```
[TASK: Weekly status update]
Summarize this week's raw notes into: Wins / Risks / Next week's priorities.
Audience: my manager. Tone: direct, no filler. Max 150 words.
```
Saved once, reused every Friday.
