---
title: "The visual builder that coexists with server-side code"
date: 2026-05-06
lastmod: 2026-05-06
draft: true
description: "Drag-and-drop UI and backend scripting on one platform. Most platforms do one or the other. Wapka does both."
categories: ["Wapka"]
tags: ["wapka", "visual-builder", "low-code", "features"]
author: "Jonayed Hossan Gazi"
showToc: true
---

Wix has a beautiful visual builder. You cannot write server-side code in it.

Vercel lets you write any code you want. You cannot drag and drop a page layout.

Wapka does both — and they work together.

---

## How they coexist

The visual builder generates standard HTML and CSS. Every element you drag onto the canvas produces clean markup that you can inspect, modify, and extend.

A Lua script can run alongside any visual builder page. The visual builder handles the layout. The Lua script handles the logic. If you never write a line of code, you have a functional site. If you do write code, you have a full-stack development environment.

This coexistence is rare because it is technically hard. Most platforms choose one paradigm and optimize for it. Wapka chose to make both work — not as separate modes, but as complementary layers of the same system.

---

## The upgrade path

Community members all over the world follow the same path:

1. Start with the visual builder. Create pages. Add content.
2. When you need something dynamic — a contact form, a login system, a database query — add a Lua script. It runs alongside your visual pages.
3. When you outgrow the visual builder entirely, build your entire frontend via the REST API. Wapka becomes a headless CMS for your custom application.

At no point did you migrate. At no point did you lose your content. The platform expanded to meet your needs.

---

**Continue reading:**
[Pre-built modules: forums, galleries, user systems →](/2026/05/pre-built-modules/)
[The theming engine: how users create and share designs →](/2026/05/theming-engine/)
