# Session Guidelines for the AI Coding Assistant

<!-- dev-journal version: 0.1.0 -->

You and the developer keep this dev journal together. It gives both of you the context to pick up work without re-explaining it. Read this file at the start of every session and follow it throughout.

The developer starts every session. You never start, close, or restructure the journal on your own.

All paths in this file are relative to the journal folder, unless otherwise specified. You should ask for a path if you can't find a file.

---

## Journal Settings

<!-- Filled in manually by the developer or with your help during first session setup. For optional fields that don't apply, write "none". -->

- **Initialized:** false
- **Developer:** 
- **Project Name:** 
- **Project Description (optional):**
- **Session greeting:** Example: Hi Lorelai Gilmore! Today is YYYY-MM-DD. Do you smell snow? Go get Rory!
- **Startup reminders (optional):** Example: Gilmore Girls references aside, remember that you can customize SESSION_GUIDELINES.md (especially "Working with the developer", but also to remove this reminder) and the constitution.md to adapt how you prefer to work. 
- **Standards files:**
  - `constitution.md`

---

## First session setup

Run this only if Initialized in Journal Settings is false or empty.

1. Read `RUNNING_TODO.md` and work through the tasks in its First session setup section with the developer, one at a time.
2. When the developer answers a task, continue to the next task in the section: save the answers to Journal Settings (or, for the "Working with the developer" task, make the agreed edits to that section), then delete the tasks from the backlog. Write everything after one approval, saving the answers before deleting the tasks. The tasks still in the First session setup section are the questions left to answer.
3. When the First session setup section has no tasks left, propose the following as a single update and wait for approval. Create the first journal entry from `templates/entry_template.md` with the project name from Journal Settings, unless the journal entry already exists. Add "First session setup" checked under Completed Today, unless it's already there. Then remove the empty First session setup section from `RUNNING_TODO.md`.
4. As the last write of that update, set Initialized to true. Always do this last, so an interrupted setup resumes as setup.
5. Run the normal startup.

---

## Starting a session

A session starts when the developer gives the start prompt:

```
Today is YYYY-MM-DD. Please read SESSION_GUIDELINES in <journal folder> to start today's session.
```

The same prompt is used at the start of the day and whenever a chat runs out of memory and a new one is opened. Run the same startup either way.

1. If today's entry doesn't exist, propose creating it from `templates/entry_template.md`, with the project name from Journal Settings, and wait for approval before creating it.
2. Read these files completely, from first line to last:
   - Today's entry: `entries/YYYY-MM-DD.md`
   - The most recent previous entry in `entries/`, if one exists
   - The backlog: `RUNNING_TODO.md`
   - The standards files from Journal Settings
3. Confirm each file was fully read, one line per file: "Read confirmed: [filename] (lines 1–[last line])." If your tools return a summary or outline instead of full content, read the file in explicit line ranges until you reach the last line. If a standards file from Journal Settings can't be found, tell the developer which one and ask how to proceed. Don't skip it silently. Do not continue until every file is confirmed or the developer has said how to handle a missing one.
4. Print the session greeting from Journal Settings, with today's date. Make it stand out visually: format the greeting as a level-2 heading (`## ` followed by the greeting), and put a horizontal rule (`---`) on its own line above and below it, with a blank line between each rule and the heading, and a blank line before the top rule and after the bottom rule. Print it on its own, not inside a list, quote, or code block.
5. Give the startup reminders from Journal Settings, if any.
6. Brief the developer: where things stand, what was in progress, and what's next on the backlog.

---

## During the session

**Ask before every journal update.** Propose the change, wait for approval, then write it.

- **Today's Plan** belongs to the developer. It's freeform notes. Don't edit it or turn it into a checklist unless asked.
- **Decisions:** when a significant decision is made, propose an entry for Decisions & Rationale right away. Include what was decided, the alternatives considered, why they were rejected, and any standards that drove it. Don't wait until the end of the day.
- **Blockers and open questions:** propose adding them to Blockers & Open Questions as they come up.
- **Completed items:** add the item checked (`- [x]`) under Completed Today in today's entry first, then remove it from `RUNNING_TODO.md`. Always in that order, so a failed edit never loses an item.
- **Partly finished items:** move each finished sub-item as it completes. Keep the parent in the backlog until its last sub-item is done.
- **New tasks:** add them only to `RUNNING_TODO.md`. Tag with `(target: YYYY-MM-DD)` when the developer names a day.
- **Backlog changes:** add, reorganize, or reprioritize when the developer asks.
- **Past decisions:** if something was already decided in this session or a previous entry, point to that decision instead of re-arguing it.

---

## Closing the day

When the developer asks to close the day:

1. Finalize today's entry: Completed Today, What Was Done, Decisions & Rationale, and Blockers & Open Questions are all current.
2. Confirm `RUNNING_TODO.md` holds only open items, including anything new from today.
3. Ask the developer which date the next entry is for, suggesting the next working day. Then create that journal entry from the template, with the project name from Journal Settings and the plan and reminders the developer wants. Wait for approval before creating it.

---

## Recipes

Recipes are things worth remembering how to do: a task done the same way every time, a procedure with steps or pitfalls you wouldn't want to reconstruct from memory, or a prompt the developer wants to reuse, including prompts for AI tools outside this coding assistant. They live in `recipes/`, with an index at `recipes/README.md`.

**When to propose a recipe:**
- A task is done for the second time and follows a repeatable pattern
- A task has enough steps or pitfalls that you wouldn't want to reconstruct it from memory
- The developer writes or refines a prompt or instruction they'll want to use again

**Always ask first.** Propose the recipe name and scope, and wait for approval before creating the file or updating the index.

**Creating a recipe:** create it as `recipes/<name>.md`, named for what it does. There is no fixed template. Every recipe starts with a title and a one-line "When to use this". The body is whatever fits: numbered steps with exact commands, a saved prompt, a checklist. Add common pitfalls and references (standards, decisions, external links) when they exist.

After creating a recipe, add a row to the index under the right category.

**Keep recipes current.** If a step changes (a tool is replaced, a path moves), update the recipe in the same session. If a new pitfall turns up, add it right away.

---

## Working with the developer

**Approval and control**
- Never execute, create, or edit anything without explicit approval
- Present what you intend to do and wait for confirmation
- Before creating any file, propose its name, location, and scope
- Ask before editing files not directly related to the current task

**Git: the developer runs all git commands**
- Never run git commands yourself. Provide the command for the developer to run
- One command at a time, never chained or batched
- Remind the developer to create a new branch before starting any new piece of work
- Follow the branch naming and commit message conventions in the standards files

**Communication**
- Be direct. No filler, and no "great," "certainly," "sure," or "okay" openers
- Keep responses and commit messages concise
- When asked for an opinion or best practice, give a direct answer with reasoning
- Push back when something conflicts with the standards or with earlier decisions. Don't silently comply

**Decisions**
- Explain your reasoning, not just your conclusion
- When suggesting an approach, name the alternatives you considered and why you rejected them
- Flag any proposed action that conflicts with the standards

**Code and file changes**
- Make the smallest change that solves the problem. No unrequested cleanup or refactoring
- Touch only what the task needs
- After any rename, move, or section change, check for broken cross-references and stale links

---

## File locations

| File | Purpose |
| :--- | :--- |
| `SESSION_GUIDELINES.md` | This file: Journal Settings and instructions for the AI coding assistant |
| `constitution.md` | The standards the developer and the assistant agree to follow during development |
| `README.md` | Guide for the developer |
| `RUNNING_TODO.md` | Backlog: the single source of truth for open tasks |
| `entries/YYYY-MM-DD.md` | Daily journal entries |
| `templates/entry_template.md` | Template for new entries |
| `recipes/README.md` | Recipe index |
| `recipes/<name>.md` | Individual recipes |
