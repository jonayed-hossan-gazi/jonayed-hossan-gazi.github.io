---
title: "The Express-like Lua framework: familiar syntax, sandboxed runtime"
date: 2026-05-06
lastmod: 2026-05-06
draft: true
description: "Wapka's Lua framework looks like Express.js, runs in a secure sandbox, and lets anyone write server-side code."
categories: ["Wapka"]
tags: ["wapka", "lua", "luajit", "framework"]
author: "Jonayed Hossan Gazi"
showToc: true
---

If you have used Express.js, Koa, or Sinatra, Wapka's Lua framework will feel immediately familiar. The syntax is designed to be recognizable — on purpose.

---

## A quick tour

```lua
local app = framework()

app:get("/", function(ctx)
    return ctx:html("<h1>Hello from Lua</h1>")
end)

app:get("/api/users", function(ctx)
    local users = db:query("SELECT id, name FROM users")
    return ctx:json(users)
end)

app:post("/api/contact", function(ctx)
    local name = ctx.body.name
    local email = ctx.body.email
    db:execute("INSERT INTO messages (name, email) VALUES (?, ?)", name, email)
    return ctx:json({success = true})
end)

app:run()
```

Route definitions. Request parameters. Database queries. JSON responses. Standard web development patterns — running inside a sandboxed LuaJIT environment.

---

## What the framework provides

- **Routing**: `app:get`, `app:post`, `app:put`, `app:delete` — standard HTTP method routing
- **Parameter parsing**: URL params (`:id`), query strings, request bodies
- **Response formatting**: HTML, JSON, plain text, file downloads
- **Database access**: Query builder with parameterized queries
- **Session management**: User authentication state across requests
- **File access**: Read and write files in the user's storage

All of this runs with kilobyte memory footprints and microsecond startup times.

---

## Why the Express-like design

When we designed the framework, we had a choice: invent a new DSL, or model it after something millions of developers already know. We chose the latter.

Familiarity lowers the barrier. A developer who knows Express can pick up Wapka's Lua framework in minutes. The concepts transfer. The syntax transfers. The mental model transfers.

For the platform's target audience — students learning backend development, creators adding their first dynamic features — this familiarity is the difference between "I can do this" and "I need to learn an entirely new system."

---

**Continue reading:**
[Why Lua? The architectural decision →](/2026/05/why-lua/)
[The database builder: visual CRUD without SQL →](/2026/05/database-builder/)
