---
title: "The detach/reattach protocol: how it works"
date: 2026-05-06
lastmod: 2026-06-05
draft: false
description: "Export your database. Run Docker. Your site is live on your server. Reattach anytime. Here is the technical walkthrough."
categories: ["Wapka"]
tags: ["wapka", "self-hosting", "docker", "freedom"]
author: "Jonayed Hossan Gazi"
showToc: true
---

The detach/reattach cycle is the practical implementation of Wapka's philosophy: users own their data and can leave anytime. Here is exactly how it works.

---

## Step 1: Detach from the managed cloud

From your dashboard:
1. Export your data. The Dataset produces a portable JSON export. (Enterprise users can also request a full database clone.)
2. Download your files. The file manager lets you export your entire storage directory as an archive.
3. Your site is now independent. Nothing remains on Wapka's servers that you do not have locally.

---

## Step 2: Self-host

On your own server:
1. Clone the Wapka repository from GitHub (`wapka-web`)  
2. Run `docker compose up` (enterprise tier; public self-hosting coming soon)
3. Import your data  
4. Copy your files to the storage directory  
5. Point your DNS to your server  

Your site is live. Same software. Same behavior. No license check. An independent node.

---

## Step 3: Reattach (if you want to)

Changed your mind about self-hosting?
1. Export your self-hosted data  
2. Import it back into your Wapka cloud account  
3. Point DNS back to Wapka  
4. Your site continues where it left off  

No data loss. No migration scripts. No version conflicts. This bidirectional migration is possible because the managed cloud and independent instances run the same software against the same data format.

---

## Why this matters

Most platforms offer export as a checkbox — a CSV file that technically contains your data but practically requires weeks of work to turn into a working site.

Wapka's detach/reattach is different because it is not an afterthought. The platform was designed with data portability from the start. Self-hosting via Docker is currently available at the enterprise tier and will be opened to all users soon.

Community members around the world — developers testing self-hosted setups, students learning infrastructure, businesses evaluating their hosting options — all will have access to the same escape hatch. It is not a premium feature. It is a fundamental right.

---

**Continue reading:**
[You can leave anytime →](/2026/05/doors-open-both-ways/)
[Self-host vs managed: honest tradeoffs →](/2026/05/self-host-vs-managed/)
