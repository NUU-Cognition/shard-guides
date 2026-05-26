# Guides

Create and manage how-to guides — instructional documents that teach readers how to accomplish specific tasks or understand specific topics. Guides come in two modes: simple single-page guides and multi-page guides with sub-sections.

## Philosophy

Guides are standalone, publishable artifacts. They should read coherently on their own and hold up outside the workspace context they were written in.

But real readers come with knowledge gaps. A guide can be expanded over time by dropping `%%? question%%` markers inline — questions a reader (or author) would naturally ask at that point in the text. The [[dev-wkfl-gide-expand]] workflow answers these in one pass, producing two kinds of content:

- **On-topic answers** get woven directly into the prose, expanding the guide's coverage seamlessly.
- **Prerequisite answers** get placed in aside callouts (`> [!info] Aside: ...`) — they enrich the reader's understanding without diluting the guide's core narrative.

This keeps guides focused on their subject while still meeting readers where they are.

## Two Modes

| Mode | Location | Naming | Use When |
|------|----------|--------|----------|
| **Simple** | `Mesh/Types/Guides/` | `(Guide) NNN Name.md` | Topic fits in one page |
| **Multi-page** | `Mesh/Guides/(Guide) Name/` | Root + sub-guides | Topic needs multiple sections |

### Simple Guide

A single numbered file:

```
Mesh/Types/Guides/(Guide) 001 Getting Started with Shards.md
```

Get the next number with `flint helper type newnumber Guide`.

### Multi-Page Guide

A folder with a root file and sub-guide pages using dot notation:

```
Mesh/Guides/(Guide) Shard Authoring/
├── (Guide) Shard Authoring.md                    ← Root (overview + table of contents)
├── (Guide) Shard Authoring . Manifest.md         ← Sub-guide
├── (Guide) Shard Authoring . Templates.md        ← Sub-guide
└── (Guide) Shard Authoring . Testing.md          ← Sub-guide
```

**Rules:**
- Every multi-page guide gets a folder: `Mesh/Guides/(Guide) Name/`
- Root file matches folder name: `(Guide) Name.md`
- Sub-guides use dot notation: `(Guide) Name . Section.md`
- Root files list children in `children:` frontmatter
- Sub-guides link back via `parent:` frontmatter

## Lifecycle

```
draft → review → published
                     ↓
                deprecated
```

| Status | Meaning |
|--------|---------|
| `draft` | Being written, not yet ready for readers |
| `review` | Content complete, ready for review |
| `published` | Complete, available for readers |
| `deprecated` | Outdated, should not be followed |

## Tags

| Tag | Usage |
|-----|-------|
| `#gide/guide` | All guides (simple and multi-page roots) |
| `#gide/section` | Sub-guide pages in multi-page guides |

## Skills

| Skill | File | Purpose |
|-------|------|---------|
| Create Guide | `dev-sk-gide-create.md` | Create a simple single-page guide |
| Add Section | `dev-sk-gide-add_section.md` | Add a sub-guide page to a multi-page guide |

## Workflows

| Workflow | File | Purpose |
|----------|------|---------|
| Start Guide | `dev-wkfl-gide-start.md` | Design and create a multi-page guide with review |
| Update Guide | `dev-wkfl-gide-update_guide.md` | Revise an existing guide's content and structure |
| Expand Guide | `dev-wkfl-gide-expand.md` | Answer inline `%%?...%%` markers to expand a guide in one pass |

## Templates

| Template | File | Purpose |
|----------|------|---------|
| Simple Guide | `dev-tmp-gide-simple-v0.1.md` | Single-page guide |
| Root Guide | `dev-tmp-gide-root-v0.1.md` | Multi-page guide root file |
| Section | `dev-tmp-gide-section-v0.1.md` | Sub-guide page |
