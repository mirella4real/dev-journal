# Dev Journal

A shared journal for a developer and their AI coding assistant. It keeps the context, decisions, and open work of a project in one place that both of you read and write, so no session starts from zero and the human stays in control of every change.

Works with any AI coding assistant that can read and edit files in your project.

<!-- Draft: structure and wording still being fine-tuned. -->

---

## Why this exists

I built this for my own projects in October 2026, after watching where AI coding tools were heading: more autonomy, longer unattended runs, fewer moments where a person has to say yes. The output gets faster and the developer understands less of it. Two weeks later nobody can explain why the code looks the way it does.

I wanted the opposite. Not a brake on the assistant, but a way of working where the human stays in the process: present at each step, making the decisions, and able to hand the work to a future self or a teammate without archaeology. The instruction files that tools offer, such as CLAUDE.md, tell the assistant how to behave. Nothing held the state of the work itself: what was decided, what was rejected and why, what is half done.

So the journal is a shared record that the developer and the assistant write together, with the developer as the decision point by protocol rather than by habit. It is tool-agnostic because what is being shared is a working practice, not an integration.

It is published so other developers can use it, and so the practice has a dated, public origin.

Mirella Batista, October 2026

## Why use it

Reasons developers adopt a dev journal. This list grows as we hear from people using it.

- **Context switching without losing your place.** Move between two or more projects and pick up each one exactly where you left it. The journal records where things stand, what was in progress, and what's next, so the cost of switching drops to one start prompt.
- **Stop re-explaining your project to every new chat.** Each session begins with the assistant reading the journal and briefing you. You don't rebuild context by hand when a chat runs out of memory or a new day starts.
- **Keep your reasoning, not just your code.** Decisions are recorded as they're made, with the alternatives considered and why they were rejected. You, your assistant, or another developer can look up why something is the way it is months later.
- **Hand work off cleanly.** When someone else picks up a project, the journal tells them where to start: open tasks, recent decisions, and known blockers. No archaeology through commit history or chat logs.
- **Keep the human in the process.** The assistant proposes; you approve. Every journal update, file change, and git command goes through you. The journal makes that protocol explicit instead of hoping the assistant behaves.

## Who it's for

Any developer who works with an AI coding assistant. The journal is deliberately generic and adaptable:

- A solo developer tired of providing context at the start of every chat.
- A developer who wants to capture their reasoning and decisions in a journal that they, their assistant, or other developers can refer back to.
- A team that wants a consistent, reviewable record of AI-assisted work.

## Human in the process

The journal is built on one stance: the assistant proposes, the developer decides. That isn't a brake on productivity. It's how you stay the person who understands and is accountable for the work.

It's fine, and encouraged, to ask your assistant to slow down:

- **Work through things step by step.** Ask for one change at a time instead of a finished batch. You see each move and can stop or redirect before the next one.
- **Explain, don't just conclude.** Ask why this approach, what the alternatives were, and why they were rejected. If the reasoning doesn't hold up, you've caught it before it's in your code.
- **Ask clarifying questions.** If you don't follow something, say so. A good assistant restates it differently rather than pressing on.
- **Challenge the approach.** Push back when something feels wrong, conflicts with your standards, or contradicts a decision you already made. Expect the assistant to push back too, and to point at the earlier decision instead of re-arguing it.
- **Approve every change.** Journal updates, file edits, and git commands all wait for your yes. Nothing happens because the assistant assumed.

These expectations aren't just advice. The template's `SESSION_GUIDELINES.md` has a "Working with the developer" section that turns them into rules the assistant reads at the start of every session: present the intent before acting, explain reasoning and name alternatives, flag conflicts with the standards, leave git commands to you. That section is yours to edit. If something here resonates, add it there and it travels with every chat. Some examples:

- "Before a change with more than one step, list the steps and wait for my go-ahead on each."
- "When I ask a question, answer it. Don't start editing until I ask for a change."
- "When you're unsure, say so and tell me what would settle it."
- "When I challenge an approach, engage with the objection. Don't just switch to what I said."
- "When you explain something, use plain language and one concrete example."

The journal entries then capture the reasoning, so the decisions you worked through together are still there when you need them.

## How it differs from CLAUDE.md or a notes file

**CLAUDE.md** (and its equivalents in other tools) tells the assistant how to behave. It is static instructions, specific to one tool, and it records nothing about what happened. A dev journal is a dated, living record of what was done, what was decided, and what's still open. It is tool-agnostic, and both the developer and the assistant read and write it. The two complement each other: CLAUDE.md can point at the journal.

**An assistant's own memory** (Claude Code's memory directory, or its equivalent elsewhere) persists across sessions, but it belongs to the tool, not the project. The assistant writes it on its own judgment, it lives outside your repository, and it is gone when you switch tools. A dev journal is written with your approval, lives with the code, and works with any assistant. The two can coexist: the journal is the record, memory is the assistant's private notes about how to work with you.

**A notes file** has no structure and no protocol. A dev journal has both:

- A startup procedure the assistant follows every session: read the journal, confirm what was read, brief the developer.
- A defined lifecycle for tasks: from the backlog, to a day's completed list, never lost between the two.
- An approval rule for every change, which is what enforces human-in-the-loop rather than just encouraging it.
- A standards document (the constitution) the assistant is held to, which the developer can adapt.

## What's in the template

| File | Purpose |
|---|---|
| `SESSION_GUIDELINES.md` | The assistant's governing instructions: how to start a session, update the journal, and work with the developer |
| `README.md` | Developer's guide to the journal and the session start prompt |
| `RUNNING_TODO.md` | The backlog: single source of truth for open tasks |
| `entries/YYYY-MM-DD.md` | One entry per working day: plan, completed work, what was done, decisions, blockers |
| `recipes/` | Things worth remembering how to do: repeatable tasks, procedures with pitfalls, and prompts worth reusing. Freeform Markdown with an index |
| `templates/` | Template for new daily entries |
| `constitution.md` | A slimmed-down set of development standards the assistant follows. Adapt it to your preferences and needs |
| `constitution-enterprise.md` | An example of an enterprise-level constitution, for teams that need stronger controls |

## Getting started

1. Copy `dev-journal-template/` into your project. The suggested location is `.local-docs/dev-journal/`.
2. Add `.local-docs/` to your `.gitignore` if you want the journal private to your machine. See the next section for the team option.
3. Open a session with your assistant and paste the start prompt, replacing the date:

   ```
   Today is YYYY-MM-DD. Please read SESSION_GUIDELINES in .local-docs/dev-journal to start today's session.
   ```

4. The first session walks you through setup: your name, project name, a greeting, and which standards file to use. After that, every session starts with the same prompt.

## Using it in a team

If a team wants to commit their journals, treat them as documentation as code: keep them in the repository in a `dev-journals/` directory with one folder per developer, for example `dev-journals/<developer-name>/`, and change them through the same branches and pull requests as everything else. A teammate picking up someone else's work then has a quick reference for where to start: that developer's latest entry, open backlog, and decisions.

## Repository layout

```
dev-journal/
├── README.md                 this file
├── dev-journal-template/     the published template; copy this into your project
└── .local-docs/dev-journal/  this repo's own journal, gitignored (we use the template to build it)
```

## Status

Early and in active use. The template carries a version comment in `SESSION_GUIDELINES.md` (currently 0.1.0). Expect the structure to change while it's being fine-tuned.

## License

MIT. See [LICENSE](LICENSE).
