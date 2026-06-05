---
title: "How Wapka's request router handles three eras simultaneously"
date: 2026-05-06
lastmod: 2026-05-06
draft: true
description: "One incoming request. Three possible handlers. Here is the technical architecture that makes it work."
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
If the request matches a Lua route, the sandboxed LuaJIT runtime executes the script. It has access to the database, file storage, session data, and request context. The script returns a response, and the engine handles serialization.

**Step 4: PHP fallback**
If no specific route matches, the PHP core renders the visual builder page or CMS content. This is the default handler that powers most user sites.

---

## The unified data layer

The critical design decision: all three handlers share the same data.

- The user table is the same whether accessed via WAP tag, Lua script, or PHP
- File storage is the same across all handlers
- Session management is unified
- CMS content is readable by any handler

This means a user can start with a WAP tag page, add a visual builder section, and later write a Lua script that queries the same database — all without migration.

---

## Performance characteristics

Because LuaJIT is so fast and the legacy parser is so simple, the dispatch overhead is negligible. In benchmarks, the router adds less than a millisecond to request processing time. The real work happens in the handler — and LuaJIT handles that at near-C speed.

---

**Continue reading:**
[A decade of code, zero forced migrations →](/2026/05/decade-of-compatibility/)
[The Express-like Lua framework →](/2026/05/lua-framework/)
