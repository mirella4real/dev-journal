# Dev Journal — Human Reference

Welcome to the Dev Journal! A shared space for humans and AI Code assistants where concept of "human in the process" is celebrated and enabled.

---

## How to start a session with your AI code assistant

Paste this prompt at the start of every session, replacing the date:

```
Today is YYYY-MM-DD. Please read SESSION_GUIDELINES in `.local-docs/dev-journal` to start today's session.
```

The AI code assistant will then follow `SESSION_GUIDELINES.md` to initialize, read the journal and constitutions, confirm what was read, and tell you what's next.

---

## File guide

| File | Purpose | Audience |
|---|---|---|
| `README.md` | This file — human reference and session start prompt | You |
| `SESSION_GUIDELINES.md` | AI code assistant's governing instructions for every session | AI CA |
| `RUNNING_TODO.md` | Backlog of open tasks | Both |
| `entries/YYYY-MM-DD.md` | Daily session journal entries | Both |
| `templates/entry_template.md` | Template for new daily journal entries | You |
| `recipes/README.md` | Searchable recipe index | Both |
| `recipes/<name>.md` | Individual how-to recipes | Both |

---

## How to create a new journal entry

1. Copy `templates/entry_template.md`
2. Rename it to today's date: `YYYY-MM-DD.md` and place it in `entries/`
3. Fill in Today's Plan before starting work

Or ask your AI code assistant — if no entry exists for today, they will propose creating one from the template and wait for your approval.

---

## Key rules (for your reference)

- **You run all git commands** — The AI code assistant provides the command, you execute it
- **One branch per feature or task** — create before starting any new piece of work
- **Branches and commit messages:** follow the version control section of your constitution. If it doesn't have one, the AI code assistant will offer to add one from §4 of `constitution-enterprise.md`
- **Decisions get recorded immediately** — don't wait until end of session
- **Done items move from `RUNNING_TODO.md` to the day's entry** (under Completed Today)
