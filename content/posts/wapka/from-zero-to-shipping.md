---
title: "From zero coding knowledge to shipping a platform"
date: 2026-05-06
lastmod: 2026-05-06
draft: true
description: "I didn't know how to code. I knew I needed to learn. Here's what 2 years of focused work actually looked like."
categories: ["Wapka"]
tags: ["wapka", "founder-story", "learning-to-code", "prototyping"]
author: "Jonayed Hossan Gazi"
showToc: true
---

When I decided to rebuild Wapka, I had a problem: I didn't know how to build a web platform.

I knew basic HTML and CSS from my time as a Wapka user. I understood the concept of a database because Wapka let you create simple tables. But I had never written a server. Never provisioned hosting. Never deployed an application. Never touched PHP, never configured NGINX, never thought about SSL certificates or DNS records or rate limiting.

I had one thing: I knew what I wanted to build. And I was willing to learn.

---

## Year one: learning and failing (2017–2018)

The first year was not glamorous. I spent months just understanding the stack. PHP? MySQL? How does a server handle requests? What's the difference between shared hosting and a VPS? None of it was obvious.

I built prototypes that barely worked. The first version couldn't even create a subdomain reliably. The file uploader broke on files larger than 2MB. The database builder was a single hardcoded table. I'd fix one thing and break three others.

This is the part people don't talk about. Learning to build something real is a process of constant failure. Each failure teaches you one small thing. Over time, those small things compound.

By the end of 2018, I had a prototype. It was ugly. It was fragile. But it could register a user, create a site, and serve a page. That was enough.

---

## Year two: from prototype to platform (2019–2020)

The second year was about making it real.

I bought domain alternatives — wapka.co, wapka.site, wapka.website — because the original .com domain was held by someone else who wanted $25,000. I didn't have $25,000. I had what I'd earned from small projects and community contributions.

I rebuilt the core engine. Moved from a single hardcoded structure to a modular system. Added the theming engine so users could customize their sites. Added file management with proper storage limits. Added the first iteration of the visual builder.

In 2020, I finally secured wapka.org. The brand was unified.

---

## What I learned about learning

You don't need to know everything to start. You need to know the next thing.

When I started, I didn't know PHP. I learned enough to build a login system. Then enough to build a file manager. Then enough to build a database abstraction layer. Each feature taught me what I needed for the next feature.

The stack I chose — PHP, MySQL, Lua, NGINX — wasn't the result of careful architectural planning. It was the result of learning what worked, one piece at a time, and keeping what survived contact with real users.

---

## The lesson

People sometimes ask what it takes to build something from scratch with no formal training.

It takes time. It takes tolerance for failure. It takes the ability to work on something for months without external validation. And it takes a reason — a real, personal reason — to keep going when progress feels invisible.

I had that reason. I wanted to bring back something that mattered to me and to a community that had scattered. That was enough.

---

**Continue reading:**
[I rebuilt a dead platform that 100,000 people now use →](/2026/05/rebuilt-a-dead-platform/)
[How I acquired the Wapka domains →](/2026/05/acquiring-wapka-domains/)
