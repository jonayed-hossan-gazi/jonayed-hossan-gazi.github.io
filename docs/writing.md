# Writing posts

## Create a new post

```bash
hugo new content posts/category/slug.md
```

This copies `archetypes/default.md` — pre-filled with my frontmatter template.

## Frontmatter checklist

```yaml
---
title: ""
date: 2026-05-06
lastmod: 2026-05-06
draft: true
description: ""       # SEO description, 1-2 sentences
categories: []
tags: []
author: "Jonayed Hossan Gazi"
showToc: true
weight: 0             # -1 = pinned to top
---
```

- Always start with `draft: true`. Flip to `false` when ready.
- Always write a `description`. It feeds meta tags, RSS, social cards.
- `weight: -1` pins a post to the homepage top.

## Categories

Use only these. Add sparingly:

| Category | For |
|---|---|
| Technology | Tech, AI, programming, tools |
| Consciousness | Philosophy, life, growth |
| Guides | Tutorials, step-by-step |
| Journal | Micro-updates, ship logs |

## Images

Pattern: `/images/posts/YYYY/MM/slug/filename.ext`

```
static/images/posts/2026/05/my-post/cover.png
static/images/posts/2026/05/my-post/diagram.png
```

Never hotlink. Everything local.

In frontmatter:
```yaml
cover:
  image: "/images/posts/2026/05/my-post/cover.png"
  alt: "Descriptive alt text"
```

In content:
```markdown
![Alt](/images/posts/2026/05/my-post/diagram.png)
```

## Post directory

```
content/posts/
├── technology/
├── consciousness/
├── guides/
├── journal/
```

Folder doesn't set the category — frontmatter does. But keeping things organized by folder keeps the repo clean as it grows.
