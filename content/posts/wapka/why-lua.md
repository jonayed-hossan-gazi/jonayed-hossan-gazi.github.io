---
title: "Why Wapka runs on Lua — the architectural decision behind it"
date: 2026-05-06
lastmod: 2026-06-05
draft: false
description: "Choosing Lua for Wapka's scripting engine wasn't a compromise. It was the only correct engineering decision for a shared hosting platform at scale."
categories: ["Wapka"]
tags: ["wapka", "lua", "lusandbox", "architecture", "sandboxing"]
author: "Jonayed Hossan Gazi"
showToc: true
---

Every platform makes a bet on its technology stack. Wapka's bet was Lua. Here's why it wasn't just a good choice — it was the only choice that made the entire platform economically possible.

---

## The problem: multi-tenant code execution

Wapka lets users write server-side scripts. That means arbitrary code from thousands of users runs on shared infrastructure. In most languages — Node.js, Python, PHP — running untrusted user code safely at scale requires containerization. Docker. MicroVMs. gVisor. These add memory overhead, startup latency, and cost.

On a shared platform with a generous free tier, that overhead kills the economics.

---

## What Lua gives you

Lua is lightweight, fast, and designed to be embedded. Wapka executes Lua inside **PHP LuaSandbox** — a secure sandbox with CPU and memory limits. Your code cannot touch the filesystem, call PHP functions, or access other sites' data. It is safe by default.

A Lua execution context uses minimal memory. Startup is near-instant. Thousands of users can run scripts concurrently on a single server without containers. The compute cost is marginal.

---

## The resource comparison

| Language | Memory per script | Startup time | Sandboxable without containers |
|---|---|---|---|
| **Node.js** | ~30 MB | Seconds | No |
| **Python** | ~20 MB | Seconds | No |
| **PHP** | ~15 MB | Instant | Partial |
| **Lua (via LuaSandbox)** | ~1 KB | Microseconds | Yes |

These numbers are not marketing — they are physics. Lua 5.1 is one of the fastest dynamic languages, and LuaSandbox enforces strict isolation at near-zero overhead.

---

## The economic consequence

The free tier exists because Lua makes it possible.

100GB storage. Free SSL. Global CDN. Server-side scripting. At $0.

If Wapka ran on Node.js or Python, the server costs would make this tier impossible. You can't give away compute that costs real money per request. But when each script execution costs essentially nothing, you can.

This isn't a loss leader. It's a structural advantage.

---

## The Express-like framework

Wapka's Lua framework is syntactically familiar to any web developer:

```lua
local app = framework()

app:get("/", function(ctx)
    return ctx:html("Hello from Lua")
end)

app:get("/api/user/:id", function(ctx)
    local user = api.users.list()
    return ctx:json(user)
end)

app:run()
```

If you've used Express.js, Koa, or Sinatra, this reads naturally. The framework handles routing, request parsing, response formatting, and database access — all inside a secure sandbox.

---

## The honest tradeoff

Lua's web ecosystem is smaller than JavaScript's or Python's. You won't find npm-scale package availability. You won't hire "Lua web developers" at the same volume.

But for the platform's target audience — creators, students, developers building full-stack apps without wanting DevOps — the tradeoff is clear: you get a fast, safe, free runtime in exchange for a language with a smaller ecosystem.

And because the platform is open source and self-hostable, you can always connect external services in any language alongside your Wapka instance.

---

**Continue reading:**
[You can leave Wapka anytime — and that is why people stay →](/2026/05/doors-open-both-ways/)
[A decade of code, zero forced migrations →](/2026/05/decade-of-compatibility/)
