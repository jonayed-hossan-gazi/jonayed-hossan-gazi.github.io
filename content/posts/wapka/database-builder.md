---
title: "The Dataset: build a data layer without writing a single query"
date: 2026-05-06
lastmod: 2026-06-05
draft: false
description: "Wapka's built-in NoSQL database — zero configuration, schemaless, fully managed. Create collections, store documents, query with filters."
categories: ["Wapka"]
tags: ["wapka", "dataset", "nosql", "database", "visual-builder"]
author: "Jonayed Hossan Gazi"
showToc: true
---

Most non-technical users never touch a database. They do not know what a collection is. They do not understand query syntax. And honestly — they should not have to.

Wapka's Dataset changes that. You store data visually. The platform handles everything else.

---

## How it works

1. **Create a collection.** Name it. Collections auto-create on first insert — no setup, no schema.
2. **Add documents.** Each document is a JSON object. Fields can be anything: text, numbers, booleans, arrays, nested objects.
3. **Query with filters.** Use the visual Dataset browser or the Lua API. Filter by exact match, ranges, patterns, and more.
4. **Display data.** Choose a view: list, grid, detail page. The platform generates the output.

No SQL. No migrations. No schema files. You define your data model as you go, and the platform turns it into a working application.

---

## Why this matters

For many users — particularly in the Wapka community across different countries and backgrounds — this is their first exposure to data modeling. They learn concepts like "documents," "collections," and "filters" not by reading a textbook, but by building something real.

Community members have used the Dataset to create:
- Movie catalogs with ratings and reviews
- Product inventories for small businesses
- Student management systems for local schools
- Event registration platforms

Each of these would normally require a developer. With the Dataset, a non-technical user can prototype and launch.

---

## Under the hood

Dataset is a NoSQL document database — think MongoDB or Firebase. Zero configuration, schemaless, and fully managed. Collections and documents are accessible from both Lua scripts and the REST API.

```lua
-- Create a document (collection "products" auto-created)
api.dataset.create("products", {
    name = "Widget",
    price = 9.99,
    inStock = true
})

-- Find documents with filters
local result = api.dataset.find("products", {
    filter = { price = { lte = 10 } }
})
```

The data is portable. Export it as JSON. Import it anywhere. No proprietary format. No lock-in.

The Dataset is not a toy. It is a rapid application development tool that happens to work without code.

---

**Continue reading:**
[The Express-like Lua framework →](/2026/05/lua-framework/)
[Pre-built modules: forums, galleries, user systems →](/2026/05/pre-built-modules/)
