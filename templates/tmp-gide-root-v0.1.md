# Filename: Mesh/Guides/(Guide) [Name]/(Guide) [Name].md

/* Multi-page guide root file. Acts as overview and table of contents.
   Create the folder first: Mesh/Guides/(Guide) [Name]/
   Sub-guides are added with sk-gide-add_section or tmp-gide-section. */

```markdown
---
id: [generate-uuid4]
tags:
  - "#gide/guide"
status: [draft|review|published|deprecated]
children:
  - "[[(Guide) [Name] . [First Section]]]"
  - (continue)
[agent]-sessions:
  - "[[agent-session-uuid]]"
template: "[[tmp-gide-root-v0.1]]"
---

# [Guide title]

## Overview

[2-4 sentences describing what this guide covers, who it's for, and what the reader will be able to do after completing it]

## Prerequisites

/* Optional — include only if there are meaningful prerequisites */

- [What the reader needs before starting]
- (continue)

## Sections

| Section | Description |
|---------|-------------|
| [[(Guide) [Name] . [Section]]] | [What this section covers] |
| (continue) |

/* The sections table is the table of contents. Keep it in reading order. */
```
