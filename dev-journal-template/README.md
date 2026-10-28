# Dev Journal: Developer's Guide

A shared record for you and your AI coding assistant. You both read and write it, so no chat session starts from zero and every change goes through you. This file is your reference. `SESSION_GUIDELINES.md` is the assistant's.

This folder was set up from the [dev-journal template](https://github.com/mirella4real/dev-journal).

---

## How to start a session

Paste this prompt at the start of every session, replacing the date. Assistants don't reliably know what day it is, so you tell them.

```
Today is YYYY-MM-DD. Please read SESSION_GUIDELINES in .local-docs/dev-journal to start today's session.
```

If the journal lives somewhere other than `.local-docs/dev-journal`, change the path in the start prompt. Use the same prompt at the start of the day and whenever a chat runs out of memory and you open a new one.

The assistant then follows `SESSION_GUIDELINES.md`: it reads today's entry, the previous one, the backlog, and the standards files, confirms what it read, greets you, and briefs you on where things stand and what's next.

On the first session, while Initialized is false in Journal Settings, it walks you through setup instead: your name, the project name, the greeting, startup reminders, the constitution, and how you like to work.

---

## File guide

| File | Purpose | Audience |
|---|---|---|
| `README.md` | This file: your reference and the session start prompt | You |
| `SESSION_GUIDELINES.md` | The assistant's governing instructions: Journal Settings, how to start a session, update the journal, and work with you | Assistant |
| `constitution.md` | The standards you and the assistant agree to follow. Adapt it or replace it with your own | Both |
| `constitution-enterprise.md` | An example enterprise-level constitution, for teams that need stronger controls. Reference only | You |
| `RUNNING_TODO.md` | The backlog: single source of truth for open tasks | Both |
| `entries/YYYY-MM-DD.md` | One entry per working day: plan, completed work, what was done, decisions, blockers | Both |
| `templates/entry_template.md` | Template for new daily entries | Both |
| `recipes/README.md` | Recipe index | Both |
| `recipes/<name>.md` | Individual recipes: repeatable tasks, procedures with pitfalls, prompts worth reusing | Both |

---

## Journal entries

The assistant proposes a new entry from the template when none exists for today, and seeds the next one when you close the day. To create one by hand, copy `templates/entry_template.md` into `entries/` as `YYYY-MM-DD.md` and fill in Today's Plan.

Today's Plan is yours: freeform notes, not a checklist. The assistant fills the other sections through the day, with your approval each time.

---

## What you can ask for

The journal is kept through plain requests. The assistant proposes the exact change and waits for your yes.

- **Record a decision.** "Record that as a decision: we chose SQLite over Postgres because this runs on one machine."
- **Add a task.** "Add to the backlog: write the export script, target Friday."
- **Mark a task done.** "The export script is done." It moves to Completed Today and comes off the backlog.
- **Note a blocker.** "Add a blocker: waiting on the API key from ops."
- **Save a recipe.** "Save how we did that as a recipe."
- **Get your bearings.** "Where did we leave off?" The assistant answers from the journal.
- **Close the day.** "Let's close the day." The assistant finalizes today's entry and seeds the next one.

---

## Key rules

- **You approve every change.** The assistant proposes journal updates, file edits, and git commands, and waits for your yes.
- **You run all git commands.** The assistant provides them, one at a time.
- **One branch per task**, created from `main` before any new piece of work. Branch names and commit messages follow the version control section of your constitution.
- **Decisions are recorded as they're made**, with the alternatives considered and why they were rejected. Not at the end of the day.
- **Done items move** from `RUNNING_TODO.md` to Completed Today in the day's entry. The backlog holds only open items.

The rules the assistant follows are in the "Working with the developer" section of `SESSION_GUIDELINES.md`. Edit that section to match how you like to work.
