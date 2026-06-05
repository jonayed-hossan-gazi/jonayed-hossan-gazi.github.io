---
title: "Real-time chat and WebSockets on shared hosting"
date: 2026-05-06
lastmod: 2026-06-05
draft: false
description: "Real-time chat, notifications, and live updates — running on shared hosting without dedicated servers. How Wapka handles WebSockets at scale."
categories: ["Wapka"]
tags: ["wapka", "websockets", "real-time", "architecture"]
author: "Jonayed Hossan Gazi"
showToc: true
---

Real-time features used to require dedicated servers. WebSockets need persistent connections. Persistent connections need resources. Most shared hosting platforms avoid real-time entirely.

Wapka supports WebSockets on shared infrastructure. Here is how.

---

## The architecture

The WebSocket layer runs alongside the HTTP server, sharing the same infrastructure. When a user connects to a chatroom or enables notifications, the platform establishes a persistent connection. Messages route through the same sandboxed environment that handles HTTP requests.

The key insight: WebSocket connections are lightweight when managed efficiently. A single server can handle thousands of concurrent connections if the underlying runtime is efficient — and Lua via LuaSandbox is exactly that.

---

## What the community built with it

Real-time chat was one of the most requested features from the community. Users building forums wanted live discussions. Users running event sites needed live updates. Students building projects wanted WebSocket experience without setting up a separate server.

Each use case, each community member's project, each feature request — all shaped how real-time support evolved. The platform reflects what people actually need.

---

**Continue reading:**
[The file manager that serves terabytes →](/2026/05/file-manager/)
[Social login, SSL, CDN — the infrastructure layer →](/2026/05/infrastructure-layer/)
