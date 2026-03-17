# Filename: Mesh/Guides/(Guide) [Parent Name]/(Guide) [Parent Name] . [Section Name].md

/* Sub-guide page within a multi-page guide. The parent root file should already exist.
   After creating this file, add it to the parent's children: frontmatter and sections table. */

```markdown
---
id: [generate-uuid4]
tags:
  - "#gide/section"
status: [draft|review|published|deprecated]
parent: "[[(Guide) [Parent Name]]]"
[agent]-sessions:
  - "[[agent-session-uuid]]"
template: "[[tmp-gide-section-v0.1]]"
authors: /* from .flint/identity.json; omit if no identity set */
  - "[[@Person Name]]"
---

# [Section title — what this section covers]

[Instructional content. Use concrete examples, code blocks, and clear steps.
 Each section should be self-contained enough to be useful on its own,
 while fitting into the larger guide narrative.]

(continue)

/* Structure the content with ## subheadings as needed.
   A section can be as short or as long as the topic requires. */
```
