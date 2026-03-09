---
id: {{uuid}}
tags:
  - "#dashboard"
  - "#gide/dashboard"
  - "#managed/shard/gide"
  - "#read-only"
---

```dataviewjs
function formatName(p) {
  return p.file.name.replace(/^\(Guide\)\s*/, '');
}

function statusIcon(status) {
  const icons = {
    'draft': '📝',
    'review': '🔍',
    'published': '✅',
    'deprecated': '🚫'
  };
  return icons[status] || '⚪';
}

function statusOrder(status) {
  const order = { 'published': 0, 'review': 1, 'draft': 2, 'deprecated': 3 };
  return order[status] ?? 99;
}

// Simple guides (numbered, in Mesh/Types/Guides/)
const simpleGuides = dv.pages('#gide/guide').where(p => p.file.path.startsWith('Mesh/Types/Guides/'));

// Multi-page guide roots (in Mesh/Guides/)
const multiGuides = dv.pages('#gide/guide').where(p => p.file.path.startsWith('Mesh/Guides/'));

// Sections (sub-guides)
const sections = dv.pages('#gide/section');

// Published Guides
dv.header(1, "Published");
const published = simpleGuides.concat(multiGuides).where(p => p.status === 'published')
  .array().sort((a, b) => a.file.name.localeCompare(b.file.name));
if (published.length === 0) {
  dv.paragraph("*None*");
} else {
  dv.table(["Guide", "Type"],
    published.map(p => [
      dv.fileLink(p.file.path, false, formatName(p)),
      p.file.path.startsWith('Mesh/Guides/') ? '📖 Multi-page' : '📄 Simple'
    ])
  );
}

// In Review
dv.header(1, "Review");
const review = simpleGuides.concat(multiGuides).where(p => p.status === 'review')
  .array().sort((a, b) => a.file.name.localeCompare(b.file.name));
if (review.length === 0) {
  dv.paragraph("*None*");
} else {
  dv.table(["Guide", "Type"],
    review.map(p => [
      dv.fileLink(p.file.path, false, formatName(p)),
      p.file.path.startsWith('Mesh/Guides/') ? '📖 Multi-page' : '📄 Simple'
    ])
  );
}

// Drafts
dv.header(1, "Drafts");
const drafts = simpleGuides.concat(multiGuides).where(p => p.status === 'draft')
  .array().sort((a, b) => a.file.name.localeCompare(b.file.name));
if (drafts.length === 0) {
  dv.paragraph("*None*");
} else {
  dv.table(["Guide", "Type"],
    drafts.map(p => [
      dv.fileLink(p.file.path, false, formatName(p)),
      p.file.path.startsWith('Mesh/Guides/') ? '📖 Multi-page' : '📄 Simple'
    ])
  );
}

// Deprecated
dv.header(1, "Deprecated");
const deprecated = simpleGuides.concat(multiGuides).where(p => p.status === 'deprecated')
  .array().sort((a, b) => a.file.name.localeCompare(b.file.name));
if (deprecated.length === 0) {
  dv.paragraph("*None*");
} else {
  dv.table(["Guide"],
    deprecated.map(p => [dv.fileLink(p.file.path, false, formatName(p))])
  );
}
```
