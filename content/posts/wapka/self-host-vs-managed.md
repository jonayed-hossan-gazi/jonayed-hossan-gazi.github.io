---
title: "Self-host vs managed: the honest tradeoffs"
date: 2026-05-06
lastmod: 2026-05-06
draft: true
description: "Run Wapka on your own server or use the managed cloud. Here is what you gain and lose with each choice."
categories: ["Wapka"]
tags: ["wapka", "self-hosting", "managed", "comparison"]
author: "Jonayed Hossan Gazi"
showToc: true
---

Wapka gives you a choice most platforms do not: use the managed cloud or self-host. Both run the same software. Both access the same database format. Both are valid.

The decision comes down to what you value.

---

## Managed cloud

| You get | You trade |
|---|---|
| 100GB free storage | Server cost (~$5-20/month) |
| Automatic SSL | You configure SSL |
| Global CDN | You configure Cloudflare |
| DDoS protection | You configure firewall |
| Built-in analytics | You install analytics |
| Automatic updates | You maintain updates |
| Support (email/priority) | Community support |
| Zero DevOps | Server management |

Managed is ideal for: creators, students, small businesses, anyone who wants to build without managing infrastructure.

Community members who use the managed cloud often contribute back in other ways — testing features, reporting bugs, helping others in forums. The relationship goes both ways.

---

## Self-hosted

| You get | You trade |
|---|---|
| Full server control | Convenience |
| No rate limits | Infrastructure features (CDN, DDoS) |
| Custom server config | Support |
| Physical data ownership | Automatic updates |
| Can add external services | Built-in analytics |

Self-host is ideal for: developers, teams with existing infrastructure, users who want complete control, projects that outgrow managed tier limits.

The self-host community is growing. Developers share configurations. Docker setups get refined. Documentation improves with every person who tries it and provides feedback.

---

## The unifying principle

Both paths are valid. Both run the same code. Both respect your data. You can switch between them anytime.

That is the point.

---

**Continue reading:**
[The detach/reattach protocol →](/2026/05/detach-reattach/)
[100GB free storage + scripting for $0 →](/2026/05/free-tier-economics/)
