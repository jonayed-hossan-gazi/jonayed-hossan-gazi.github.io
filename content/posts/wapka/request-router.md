---
title: "How Wapka's request router handles three eras simultaneously"
date: 2026-05-06
lastmod: 2026-06-05
draft: false
description: "A single web request arrives at Wapka. It could match a legacy WAP tag page, a Lua route, or a Native App. Here is the architecture that dispatches across three eras."
categories: ["Wapka"]
tags: ["wapka", "architecture", "router", "backend"]
author: "Jonayed Hossan Gazi"
showToc: true
---

A web request arrives at Wapka. It could be a WAP tag page from 2013, a visual builder page from 2020, or a Lua API endpoint from this year. The router needs to figure out which one — fast — and dispatch it to the right handler.

Here is how that works.

---

## The dispatch chain

Every incoming HTTP request passes through a priority-ordered dispatch:

**Step 1: Route matching**
The router checks the URL against registered routes. Lua scripts register routes via the framework (`app:get`, `app:post`). The REST API registers endpoints. Legacy WAP pages are mapped in the database. The router resolves the match and hands off to the correct handler.

**Step 2: Legacy parser (if matched)**
If the request targets a legacy WAP tag page, the WML parser takes over. It reads the old tag format from the database, parses `{wb_name}` type tags, and renders the response. This parser has not changed substantially in a decade — and that is the point. Stability is the feature.

**Step 3: Lua engine (if matched)**
If the request matches a Lua route, the sandboxed Lua runtime (PHP LuaSandbox) executes the script. It has access to the database, file storage, session data, and request context. The script returns a response, and the engine handles serialization.

**Step 4: Native App handler**
If no specific route matches, the Native App engine renders pre-built applications (blog, forum, store) or visual builder pages. This is the default handler that powers most user sites.

---

## The unified data layer

The critical design decision: all three handlers share the same data.

- The user table is the same whether accessed via WAP tag, Lua script, or Native App
- File storage is the same across all handlers
- Session management is unified
- CMS content is readable by any handler

This means a user can start with a WAP tag page, add a visual builder section, and later write a Lua script that queries the same database — all without migration.

---

## Performance characteristics

Because Lua is so fast and the legacy parser is so simple, the dispatch overhead is negligible. The router adds less than a millisecond to request processing time. The real work happens in the handler — and Lua handles that efficiently.

---

**Continue reading:**
[A decade of code, zero forced migrations →](/2026/05/decade-of-compatibility/)
[The Express-like Lua framework →](/2026/05/lua-framework/)
