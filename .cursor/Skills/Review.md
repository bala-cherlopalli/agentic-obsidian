---
skill: review
---

# Skill: Review

> Quick vault health check — surface anything that needs attention.

## Instructions

1. Count notes in each folder
2. List any notes in Quick Capture older than 7 days (need organizing)
3. List any notes with no tags
4. List any notes with no links to other notes
5. Summarize what's been added recently
6. List all open tasks (`done: false` in frontmatter) grouped by area and category
7. Flag any quick tasks past their `due` date
8. Flag any working tasks that haven't been modified in 14+ days

## Output

```
Quick Capture:  X notes (Y older than 7 days)
Personal:       X notes
Work:           X notes
Archive:        X notes

Open Tasks — Personal:
  Quick:
  - [[Task Name]] — due YYYY-MM-DD
  Working:
  - [[Task Name]] — last touched YYYY-MM-DD

Open Tasks — Work:
  Quick:
  - [[Task Name]] — due YYYY-MM-DD
  Working:
  - [[Task Name]] — last touched YYYY-MM-DD

Overdue / Stale:
- [[Task Name]] — due was YYYY-MM-DD (X days ago)

Needs attention:
- [list of stale captures or untagged notes]
```
