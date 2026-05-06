---
title: "The simplest blog is just text files"
date: 2026-05-06
lastmod: 2026-05-06
draft: false
weight: -2
description: "Moved zuna.id from WordPress to Hugo on GitHub Pages. No server, no database, no maintenance."
categories: ["Journal"]
tags: ["hugo", "wordpress", "migration", "github-pages"]
author: "Jonayed Hossan Gazi"
showToc: false
---

Moved my blog from WordPress to Hugo on GitHub Pages.

No more PHP. No MySQL. No `/wp-admin`. No plugin updates. No server to maintain.

Just markdown files in a Git repo. Push to deploy. Everything is pre-built HTML — there's nothing to hack, nothing to crash, nothing to patch.

---

**Why it matters**

A blog should be simple. WordPress was overkill for 25 posts. Hugo builds the entire site in under 200ms. GitHub Pages serves it for free. SSL auto-renewed. No hosting panel, no control panel, no `cron` jobs, no email alerts about outdated plugins at 2am.

Bare metal in spirit, even if it's on GitHub's infra.

---

**The migration**

Wrote a quick Python script that pulls posts from the WordPress REST API, converts HTML to Markdown, maps categories and tags, and downloads images locally. Two posts imported today. The rest queued.

---

**What I lost**: a GUI.  
**What I gained**: everything else.

This is how a personal blog should work. No maintenance. Just write and push.
