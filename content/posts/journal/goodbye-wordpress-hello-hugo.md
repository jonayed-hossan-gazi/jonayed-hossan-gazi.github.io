---
title: "Goodbye WordPress, hello Hugo"
date: 2026-05-06
lastmod: 2026-05-06
draft: false
weight: -2
description: "Why I moved a 25-post WordPress blog to static HTML — and what I gained."
categories: ["Journal"]
tags: ["hugo", "wordpress", "migration", "github-pages", "static-site"]
author: "Jonayed Hossan Gazi"
showToc: false
---

Today I hit deploy on something I should've done years ago.

**zuna.id** — my blog of 25 posts — is now a static Hugo site on GitHub Pages. No PHP. No MySQL. No `/wp-admin`. No plugin vulnerabilities. Just markdown files and a build step.

---

### Why now

WordPress was fine. But fine isn't great. I was running a CMS I didn't need for a blog that barely changed. The cognitive overhead of maintaining a WP install for 25 posts was absurd.

Hugo builds the entire site in under 200ms. Every page is pure HTML. There's nothing to hack, nothing to update, nothing to crash. The server literally cannot go down — because there is no server. Just files on a CDN.

---

### What I actually gained

- **$0 hosting cost**. GitHub Pages, free forever.
- **$0 SSL renewal**. Automatic.
- **Structured data baked in**. JSON-LD, OpenGraph, Twitter Cards — no plugin needed.
- **Full-text search**. Client-side Fuse.js. Instant. Works offline.
- **Comments via GitHub Issues**. Utterances. No database. No spam queue.
- **Dark mode**. Because it's 2026.
- **A 404 page with a fork bomb joke**. Priorities.

---

### What I lost

- The WYSIWYG editor. Replaced by VS Code and Markdown. Honestly? Better.
- The plugin ecosystem. Don't miss it. Sitemaps, RSS, SEO — all built in.
- `?p=123` URLs. Replaced by `/2026/05/slug/`. Cleaner.

---

### The migration script

Wrote a Python script that pulls posts from the WordPress REST API, maps categories and tags, downloads images, and generates Hugo-compatible Markdown with full frontmatter.

Two posts are live. 23 queued.

---

### What this means going forward

I now own my content as **plain text files in a Git repo.**

If Hugo disappears tomorrow — I still have 25 `.md` files.
If GitHub Pages shuts down — I deploy to a $5 VPS with one command.
If I disappear — the blog lives as long as someone renews the domain.

That's the point. Long-term, self-contained, zero-dependency content. Not bad for a day's work.

---

**Next:** migrate the rest. Then write something new. It's been too long.
