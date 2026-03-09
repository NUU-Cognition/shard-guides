# Guides

Create and manage how-to guides — single-page or multi-page instructional documents.

## Structure

```
Shards/(Dev) Guides/
  shard.yaml
  init-gide.md
  skills/
    sk-gide-create.md          # Create a simple guide
    sk-gide-add_section.md     # Add section to multi-page guide
  workflows/
    wkfl-gide-start.md         # Design + create multi-page guide
  templates/
    tmp-gide-simple-v0.1.md    # Simple single-page guide
    tmp-gide-root-v0.1.md      # Multi-page guide root
    tmp-gide-section-v0.1.md   # Sub-guide section
  install/
    (Dashboard) Guides.md      # DataviewJS dashboard
```

## Guide Types

**Simple:** `Mesh/Types/Guides/(Guide) NNN Name.md` — numbered, single file

**Multi-page:** `Mesh/Guides/(Guide) Name/` — folder with root + dot-notation sub-guides
