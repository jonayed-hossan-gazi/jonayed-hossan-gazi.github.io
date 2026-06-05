---
title: "Why Wapka's compute costs are near zero"
date: 2026-05-06
lastmod: 2026-06-05
draft: false
description: "Why Wapka can offer server-side scripting for free. The numbers show how Lua via PHP LuaSandbox makes compute costs near zero on shared infrastructure."
categories: ["Wapka"]
tags: ["wapka", "lua", "lusandbox", "performance", "architecture"]
author: "Jonayed Hossan Gazi"
showToc: true
---

The numbers tell the story. A Node.js process consumes roughly 30 megabytes of memory. A Python process: 20 megabytes. A Lua state inside LuaSandbox: 1 to 5 kilobytes.

That three-order-of-magnitude difference is why Wapka can offer server-side scripting for free.

---

## The runtime economics

When you let thousands of users run server-side code on shared infrastructure, the cost of each execution matters exponentially. At scale, memory and CPU are the dominant factors.

Wapka runs Lua inside **PHP LuaSandbox** — a secure sandbox with CPU and memory limits. Lua 5.1 is one of the fastest dynamic languages. Combined with its minimal memory footprint, the result is a scripting engine that costs essentially nothing to run.

This is not an accident. Lua was designed from the start to be embedded in host applications with minimal overhead. LuaSandbox enforces strict isolation at near-zero cost.

---

## Real-world impact

A single modest server running Wapka can comfortably handle thousands of concurrent Lua script executions. The same server running Node.js or Python sandboxes would struggle with dozens.

This efficiency cascades through every layer of the platform:
- More users per server
- Lower infrastructure cost
- Faster response times
- Viable free tier

The last point is the most important. Without Lua's efficiency, the free tier — 100GB storage, SSL, CDN, scripting — simply would not exist. The math would not work.

---

## What community members have built on it

People from around the world have pushed Lua to its limits on Wapka. REST APIs serving thousands of requests. Real-time chat systems. Media processing pipelines. Each one running on the same shared infrastructure, each one costing fractions of a cent to execute.

These are not hypotheticals. They are production applications built by community members who, in many cases, started with no programming experience and learned on the platform.

---

**Continue reading:**
[Why Lua? The architectural decision →](/2026/05/why-lua/)
[100GB free storage + scripting for $0 →](/2026/05/free-tier-economics/)
