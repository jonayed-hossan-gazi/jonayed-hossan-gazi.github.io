---
title: "The doors open both ways — why Wapka is built for freedom"
date: 2026-05-06
lastmod: 2026-05-06
draft: true
description: "Open source. Docker self-hosting. Raw data export. The platform gives you every path — and that builds genuine trust."
categories: ["Wapka"]
tags: ["wapka", "open-source", "self-hosting", "docker", "freedom"]
author: "Jonayed Hossan Gazi"
showToc: true
---

Most platforms build walls. Terms of service. Proprietary data formats. Export processes that technically exist but practically don't work. The message is always the same: you can join, but leaving will cost you.

Wapka takes the opposite approach. You can leave anytime. And that counterintuitive decision is exactly why people choose to stay.

---

## The open source foundation

The entire Wapka codebase is open source on GitHub at `wapka-web`. Every line. The visual builder. The Lua engine. The legacy parser. The REST API. The admin dashboard.

This isn't "open source" as a marketing badge. It's open source as an architectural decision. The code can be audited. Forked. Improved. If the managed service disappeared tomorrow, the software would continue.

Open source means you are not renting access to a proprietary black box. You are using software that belongs to the commons.

---

## The self-hosting path

You can run Wapka on your own server. The process is simple:

1. Export your database (raw SQL dump — no proprietary format)
2. Clone the repository from GitHub
3. Run `docker compose up` (PHP-FPM + MySQL)
4. Import your database
5. Point your DNS to your server

Your site runs identically to the cloud version. Same software. Same behavior. No license checks. No "call home" to Wapka servers. A truly independent node.

---

## The detach/reattach cycle

This is the feature most platforms can't offer. You can:

- **Detach**: export your site, run it independently on your own server
- **Self-host**: maintain it yourself, customize freely, add external services
- **Reattach**: if you decide managing a server isn't worth the effort, import your data back to the managed cloud

No data loss. No migration scripts. No breaking changes. You move between managed and self-hosted without burning bridges.

---

## How this compares

| Platform | Can you leave? | Your data | Self-host |
|---|---|---|---|
| Wix | No — site is locked | Proprietary | Impossible |
| WordPress.com | Yes, but painful | Export XML, serialized data | Yes, different software |
| Vercel | Frontend only | Git repo | No — edge network locked |
| **Wapka** | **Yes, seamless** | **Raw SQL dump** | **Same software, Docker** |

---

## The work in progress

Full transparency: the open source transition is ongoing. The repository at `wapka-web` contains the core platform — the PHP framework, the Lua engine, the legacy parser, the REST API, the Docker configuration. The foundation is there. Anyone can clone, build, and run a self-hosted instance today.

But there is more to do. Documentation for self-hosters needs to deepen. Upgrade paths between releases need to smooth. The module ecosystem needs to grow. Open source is not a one-time decision — it is a continuous process. We are in the middle of it.

What exists now is real and functional. What is coming will make it better. The commitment is the same: the platform belongs to the community, and the code proves it.

---

## The paradox

People sometimes ask: doesn't giving users an exit reduce retention?

The opposite happens.

When you know you can leave anytime, you trust the platform more. You build more. You invest more. You stay because you want to — not because leaving is expensive.

Trust is the scarcest resource in platform economics. Most platforms try to manufacture it with marketing. Wapka builds it into the architecture.

---

**Continue reading:**
[Why Lua? The architectural decision →](/2026/05/why-lua/)
[Wapka vs WordPress vs Wix vs Vercel →](/2026/05/wapka-vs-everyone/)
