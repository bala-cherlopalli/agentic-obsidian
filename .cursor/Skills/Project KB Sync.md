---
skill: project-kb-sync
---

# Skill: Project KB Sync

> Build or refresh a project knowledge base from an external implementation or working-project folder.

## Trigger phrases

Use this skill when the user says:

- `kb sync <project>`
- `kb build <project>`
- `kb refresh <project>`
- `update the <project> KB from source`

## Workflow

1. Read `Work/Project Registry.md` and find the project mapping.
2. Inspect the source project shallowly before reading files.
3. Read high-signal files first:
   - `README*`, `AGENTS.md`, `package.json`, `pom.xml`, `pyproject.toml`
   - `docs/`, `specs/`, `src/`, `app/`, `api/`, `schemas/`
   - project-specific markdown or design documents
   - `.specstory/history/` chat transcripts when they capture decisions, requirements, or project context
4. Ignore:
   - dependency folders such as `node_modules/`
   - generated output such as `dist/`, `build/`, `target/`
   - local cache folders such as `.history/`
   - secrets and environment files
5. Update the mapped KB folder with concise, source-aware notes.
6. Report:
   - files read
   - notes updated
   - important skipped files
   - open questions or follow-up tasks

## KB note set

For a new project KB, prefer this starter set:

- `<Project>.md` — index and source mapping
- `Implementation Overview.md`
- `Architecture Notes.md`
- `API Surface.md`
- `Source Map.md`
- `Open Questions.md`

Only create notes that are useful for the project. Do not create empty taxonomy.

## Writing rules

- Summarize durable knowledge; do not mirror the whole repository.
- Link related notes with `[[wikilinks]]`.
- Include source paths inline when they help trace a fact.
- Preserve existing notes and user edits.
- Keep tasks as `- [ ] ... #task` if they should show in Tasks plugin views.
- For chat history, summarize decisions and durable facts; do not copy long transcript blocks.
