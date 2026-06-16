# Wiki Schema
## Domain
AIPlanet GenAI Internship - tracks intern updates, progress, and work over 4-month internship (June-October 2026).
## Conventions
- File names: lowercase, hyphens, no spaces
- Every wiki page starts with YAML frontmatter
- Use [[wikilinks]] to link between pages
- When updating a page, always bump the updated date
- Every new page must be added to index.md
- Every action must be appended to log.md
## Frontmatter
```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | query
tags: [intern, week-1, week-2, hermes, slack]
sources: [raw/slack/source-file.md]
---
```
## Tag Taxonomy
- People: intern, manager
- Work: hermes, slack, google-docs, wiki, cron, skill
- Timeline: week-1, week-2, week-3, week-4
- Status: in-progress, blocked, completed
## Page Thresholds
- Create an entity page for each intern
- Update entity pages with every new Slack update
- Don't create pages for passing mentions
## Update Policy
On new intern update:
1. Save raw Slack message to raw/slack/ (immutable)
2. Read intern's entity page
3. Append new entry to History section
4. Rewrite Summary section to reflect current state
5. Bump updated date in frontmatter
6. Append to log.md
