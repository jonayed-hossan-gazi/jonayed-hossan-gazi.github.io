---
title: "A decade of code, zero forced migrations"
date: 2026-05-06
lastmod: 2026-05-06
draft: true
description: "Code from 2013 still runs on Wapka. Here is how backward compatibility became a design principle, not an afterthought."
categories: ["Wapka"]
tags: ["wapka", "architecture", "backward-compatibility", "legacy"]
author: "Jonayed Hossan Gazi"
showToc: true
---

Most platforms upgrade by breaking things. Old versions are deprecated. APIs are removed. Users are told to migrate — or lose access. It happens everywhere. WordPress plugins break on updates. Python 2 code stopped working when Python 3 shipped. iOS apps need constant rewrites to stay in the App Store.

Wapka took a different path. Code written in 2013 still runs today. Unchanged. Alongside code written this year. How is that possible — and why does it matter?

---

## The three eras of Wapka

The platform has evolved through three distinct phases:

**Era 1: WAP tags (original platform era)**
Simple markup language for mobile pages. Used tags like `{wb_name}` and `{wb_forum}` to embed dynamic content. Ran on feature phones with 128x128 screens.

**Era 2: Visual builder + CMS (modernization era)**
Drag-and-drop site builder. HTML5 output. Theming engine. Pre-built modules for forums, galleries, and user systems.

**Era 3: Lua scripting + REST API (developer era)**
Full server-side scripting with an Express-like framework. REST API for headless use cases. Docker self-hosting. MCP protocol for AI integration.

Each era added capabilities. None removed them.

---

## How it works technically

When a request arrives, Wapka's router determines how to handle it:

1. The legacy parser checks if the URL matches a WAP tag page stored in the database
2. The Lua router checks for matching script routes
3. The PHP fallback renders visual builder pages and CMS content

All three handlers access the same data layer. The same user database. The same file storage. The same session management. A visual builder page can include a Lua component. A Lua script can serve WAP tags. The REST API can read content created by any of them.

This is not three separate products stapled together. It is a single runtime with multiple interpreters that share a unified data model.

---

## Why this architecture is rare

Most platforms are built era by era. The old codebase is deprecated. The new codebase starts fresh. Migrating between them is the user's problem.

Wapka absorbed the complexity internally. Every architectural change had to satisfy a constraint: existing content must continue to render correctly. New features must not break old ones. The data format must remain stable across all interpreters.

This is harder to build. It constrains every decision. But the result is a platform where users never hear the word "deprecated."

---

## What community members built with this

Users have grown alongside the platform. Someone who built a simple WAP guestbook in 2013 can still maintain that same site while adding a modern blog with Lua-powered comments. Their content survived. Their URLs survived. Their user base survived.

This continuity is incredibly rare on the web. Most sites from 2013 are long gone — either abandoned or rebuilt from scratch on a different stack. Wapka sites from that era are still live, still functional, and have evolved in place.

---

**Continue reading:**
[Why Lua? The architectural decision →](/2026/05/why-lua/)
[How the request router handles three eras →](/2026/05/request-router/)
