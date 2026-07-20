---
skill: organize
---

# Skill: Organize

> Process Quick Capture notes — append to today's daily note by default, extract tasks as TODOs.

## Default behavior

All quick captures go into **today's daily note** at `Daily Notes/YYYY-MM-DD.md`. If the daily note doesn't exist yet, create it using `Templates/Daily.md`.

**Exceptions — create a separate note instead when:**
- The user explicitly asks to file it under a specific category, note, or group
- The content is clearly a standalone topic that deserves its own note (e.g. meeting notes for a specific project, a detailed how-to, a long-form idea)
- The content clearly belongs to an existing shallow project folder such as `Work/ILS/` or `Work/RDR/`

## Instructions

1. Read each note in `Quick Capture/`
2. Open (or create) today's daily note at `Daily Notes/YYYY-MM-DD.md`
3. Append the captured text under `## Notes`
4. Scan for actionable items — tasks, follow-ups, things to do
5. For each actionable item, add a `- [ ]` checkbox under the appropriate section:
   - `### Personal` for personal tasks
   - `### Work` for work tasks
6. Tag each task with context inline if helpful: `- [ ] Do the thing #health`
7. Delete the original Quick Capture note after processing
8. If a task is very specific to an existing note or project, add the `- [ ]` there instead and link from the daily note

## Project subfolders

Larger projects may use one shallow folder level under `Work/` or `Personal/`.

- Honor existing project folders when a capture clearly matches the project.
- Create a new project folder only when the user asks, or when several standalone notes clearly belong together.
- Keep folders shallow: use `Work/Project Name/`, not deeper nested structures.
- Add project-specific standalone task notes to the project folder.
- Prefer a simple project index note inside the folder when there are several related notes.

## Assets and resources

Organize root-level assets during the same pass.

- Move project-specific images, PDFs, spreadsheets, and other files into that project's `assets/` folder.
- Use a top-level `Assets/` folder only for shared or unclear resources.
- Preserve Obsidian embeds and links after moving files.
- Report any asset whose destination is ambiguous.

## Task format (Tasks plugin emoji format)

Use the Tasks plugin emoji markers for inline metadata on checkboxes:

```markdown
- [ ] Task description 📅 2026-02-24
- [ ] Urgent task ⏫ 📅 2026-02-24
- [ ] Medium priority task 🔼
- [ ] Low priority task 🔽
- [ ] Scheduled for later ⏳ 2026-03-01
- [x] Done task ✅ 2026-02-23
```

**Emoji reference:**
- `📅` due date
- `⏳` scheduled date
- `🛫` start date
- `✅` done date (added automatically when checked off)
- `⏫` high priority
- `🔼` medium priority
- `🔽` low priority

**When to add what:**
- Always add `📅 YYYY-MM-DD` if the task has a clear deadline or target date
- Add `⏫` for urgent / "at any cost" / "must do" items
- Skip priority emoji for normal tasks

## When to create standalone Task notes

Only create a separate Task note (in `Personal/` or `Work/`) when:
- It's a **working** item — long-running, no hard deadline, picked up over days/weeks
- The user explicitly says to

Standalone task notes use `Templates/Task.md` with frontmatter:
```yaml
---
created: "YYYY-MM-DD"
area: "personal" or "work"
category: "working"
due: ""
done: false
tags:
  - task
---
```

## Rules

- Default is always the daily note unless told otherwise
- Append, never overwrite — a daily note accumulates throughout the day
- Keep it scannable — short checkbox lines, not paragraphs
- Link to related notes with `[[wikilinks]]` when obvious
- Quick tasks (due today/tomorrow) stay in the daily note
- Working tasks (long-running) get their own note in `Personal/` or `Work/`
