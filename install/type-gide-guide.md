---
id: 7e05f1a6-e6f6-485e-bcca-2b7991258b87
tags:
  - "#f/metadata"
  - "#f/type"
---

# Guide

An instructional document that teaches how to accomplish a specific task or understand a specific topic. Guides come in two modes: simple single-page and multi-page with sub-sections.

## Properties

| Property | Value |
|----------|-------|
| Tag | `#gide/guide` |
| Location | `Mesh/Types/Guides/` (simple), `Mesh/Guides/(Guide) Name/` (multi-page) |
| Archive | `Mesh/Archive/Guides/` |
| Naming | Simple: `(Guide) NNN [Name].md` / Multi-page: `(Guide) Name . Section.md` |
| Numbering | `flint helper type newnumber Guide` (simple only) |

## Lifecycle

```
draft → review → published
                     ↓
                deprecated
```

## Templates

- [[tmp-gide-simple-v0.1]] — Single-page guide
- [[tmp-gide-root-v0.1]] — Multi-page guide root
- [[tmp-gide-section-v0.1]] — Multi-page sub-section
