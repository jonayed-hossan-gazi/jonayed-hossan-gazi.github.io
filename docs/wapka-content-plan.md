# Wapka Content Plan — Complete Series

A multi-part content strategy to establish Wapka as a platform brand.
All posts founder-authored by Jonayed Hossan Gazi.

---

## Tone principles

| Use | Avoid |
|---|---|
| "I started learning at 15" | "Kid from a poor country" |
| "Bootstrapped from zero" | "Third world, had nothing" |
| "Self-funded, reinvested every dollar" | "Couldn't afford servers" |
| "Saw an opportunity nobody took" | "Was sad when it shut down" |
| "Built regardless of circumstances" | "Impossible in my situation" |

Geography adds texture, never headlines. The story is ambition, execution, scale.

Every post: founder voice. Clear. Confident. Honest about tradeoffs. Zero marketing fluff.

---

## Post structure rules

- **1 clear message per post.** Split, don't cram.
- **500–1500 words.** Long enough to matter, short enough to read.
- **Cross-link 2–3 others** at the bottom.
- **1 image per post** (screenshot, diagram, or abstract).
- **SEO**: title 50–60 chars, description 120–155 chars.
- **Category**: `Wapka` for all posts.
- **Tags**: topic-specific + `wapka` always.

---

## PART 1 — THE FOUNDER'S STORY (6 posts)

### 1.1 — I rebuilt a dead platform that 100,000 people now use
The origin. A platform shut down. A community scattered. One person decided to bring it back. The decision and the conviction behind it.

**Source**: `draft/wapka-history.txt` lines 1–4, 19

### 1.2 — From zero coding knowledge to shipping a platform
The 2-year grind. Prototypes. Failures. Teaching yourself a stack from nothing. Not a talent story — a process story.

**Source**: `draft/wapka-history.txt` lines 5–19

### 1.3 — How I acquired the Wapka domains without the .com
Offered $4,000. Got rejected — they wanted $25,000. The alternative strategy: bought wapka.co, then .site, .website, and finally .org. Building a brand without the premium domain.

**Source**: `draft/wapka-history.txt` lines 5–18

### 1.4 — Keeping terabytes of user data alive for a decade — on my own
Users uploaded media streaming sites. Terabytes of files. Bandwidth bills. Storage costs. No one pays — the platform was free. For years, I covered everything from personal savings, ad revenue, and community contributions. The invisible cost of keeping a promise.

**Source**: `draft/wapka-history.txt` lines 26–28

### 1.5 — Why I introduced paid plans after 5 years of free
Free forever was the promise. But storage at scale costs real money. The decision to add paid tiers — not to profit, but to survive. How the community reacted. What the paid plans actually offer.

**Source**: `draft/wapka-history.txt` lines 26–28

### 1.6 — What 10 years of building teaches you about focus
The founder reflection. Consistency over intensity. Iteration over perfection. Backward compatibility over rewrites. The lessons that only come from staying with one thing.

**Source**: original reflection

---

## PART 2 — THE TECHNICAL ARCHITECTURE (6 posts)

### 2.1 — Why Lua? The architectural bet behind Wapka's scripting engine
Sandboxed multi-tenancy at zero marginal cost. Node and Python can't do this economically. Lua wasn't a compromise — it was the only correct choice.

**Source**: `draft/wapka-1.txt`, `draft/wapka-2.txt`

### 2.2 — A decade of code, zero forced migrations
WAP tags from 2013. Visual builder from 2018. Lua scripts from 2024. REST APIs from 2026. All on one data layer. This is not technical debt — it's a design principle.

**Source**: `draft/wapka-2.txt`, `draft/wapka-5.txt` Part 3

### 2.3 — How Wapka's request router handles three eras simultaneously
The technical deep dive. One incoming request. Three possible handlers: legacy parser, modern Lua router, PHP fallback. How they coexist without conflict.

**Source**: `draft/wapka-2.txt` lines 8–10, `draft/wapka-5.txt` lines 158–170

### 2.4 — The Express-like Lua framework: familiar syntax, sandboxed runtime
Walking through the `app:get()`, `app:post()`, request/response cycle. Looks like Express.js. Runs in a sandbox. Why the API design matters.

**Source**: `draft/wapka-5.txt` lines 124–137

### 2.5 — The database builder: visual CRUD without writing SQL
Non-technical users can create relational databases — tables, forms, relationships — without a single SQL query. This is the feature most people discover and fall in love with.

**Source**: `draft/wapka-history.txt` lines 84–88

### 2.6 — LuaJIT: why compute costs near zero on Wapka
Memory: kilobytes per script. Startup: microseconds. CPU: near-C speed. The free tier doesn't exist because of marketing — it exists because of physics.

**Source**: `draft/wapka-5.txt` lines 112–119, `draft/wapka-2.txt` lines 10–14

---

## PART 3 — PLATFORM FEATURES DEEP DIVE (6 posts)

### 3.1 — The visual builder meets server-side code: a rare combination
Drag-and-drop UI + backend scripting on the same platform. Wix can't do server-side. Vercel can't do visual. This is the gap.

**Source**: `draft/wapka-0.txt` line 7, `draft/wapka-1.txt` lines 21–22

### 3.2 — Pre-built modules: forums, galleries, user systems in one click
Forums, chatrooms, guestbooks, galleries, user auth — all pre-installed. No plugin marketplace needed. It just works.

**Source**: `draft/wapka-history.txt` lines 39–46, `draft/wapka-0.txt` line 10

### 3.3 — The theming engine: how users create and share designs
.thm and .tpl files. The community creates skins. Neon colors, scrolling marquee, custom CSS. The creative culture of Wapka.

**Source**: `draft/wapka-history.txt` lines 56–57

### 3.4 — Real-time features on shared hosting: WebSockets and beyond
WebSockets, chat, notifications — running on shared infrastructure. No dedicated server needed. How the architecture handles real-time at scale.

**Source**: `draft/wapka-history.txt` line 95

### 3.5 — The file manager that serves terabytes without breaking
Users upload massive files. Media streaming sites. The file manager handles it. Storage strategies at scale.

**Source**: `draft/wapka-history.txt` lines 27, 44

### 3.6 — Social login, SSL, CDN — the infrastructure layer
Google/Facebook login. Free SSL certificates. Global CDN. DDoS protection. The managed service handles DevOps so users don't have to.

**Source**: `draft/wapka-history.txt` lines 92–94, `draft/wapka-5.txt` lines 252–258

---

## PART 4 — OPEN SOURCE & FREEDOM (4 posts)

### 4.1 — You can leave Wapka anytime — and that's why people stay
Open source on GitHub. Docker self-hosting. Raw database export. Detach/reattach cycle. The counterintuitive trust model.

**Source**: `draft/wapka-3.txt`, `draft/wapka-4.txt`

### 4.2 — The detach/reattach protocol explained
Technical walkthrough. Export DB → Docker up → point DNS → site is live. Reattach anytime. No data loss. No proprietary barriers.

**Source**: `draft/wapka-3.txt` lines 28–33, `draft/wapka-4.txt` lines 37–43

### 4.3 — Self-host vs managed: the honest tradeoffs
What you get with the cloud (CDN, SSL, DDoS, support, 100GB free). What you lose self-hosting (infra features, convenience). A fair comparison, no bias.

**Source**: `draft/wapka-4.txt` lines 38–45, `draft/wapka-5.txt` lines 247–273

### 4.4 — 100GB free storage + server-side scripting for $0
The economics. Lua's efficiency makes this possible. Every competitor burns money on compute. Wapka barely uses any. This is the structural advantage that can't be copied.

**Source**: `draft/wapka-4.txt` line 1, `draft/wapka-5.txt` Part 8.3

---

## PART 5 — POSITIONING & AUDIENCE (5 posts)

### 5.1 — Wapka vs WordPress vs Wix vs Vercel
Honest head-to-head. Who should use what. Where Wapka wins. Where it doesn't. Transparency builds trust.

**Source**: `draft/wapka-5.txt` Part 7

### 5.2 — Between Wix and Vercel there's a void
The market gap. Beginners locked into walled gardens. Developers buried in DevOps. No middle ground. Wapka fills it.

**Source**: `draft/wapka-0.txt`, `draft/wapka-5.txt` Parts 1, 7

### 5.3 — Why Wapka is the best platform for students learning to code
Zero cost. Visual start. Gradual path to scripting. No credit card. No DevOps. The ideal learning environment.

**Source**: `draft/wapka-history.txt` lines 101–102, `draft/wapka-5.txt` lines 353–374

### 5.4 — From Wapka user to Wapka developer: the career path
The upgrade path. Visual builder → Lua scripting → REST API → self-hosting. One platform at every skill level. No migration needed.

**Source**: `draft/wapka-5.txt` lines 66–67, 366–374

### 5.5 — Building for the long tail, not the enterprise
Wapka doesn't target enterprises. It targets individuals, creators, students, small teams. Why serving the long tail is a defensible strategy.

**Source**: original argument

---

## PART 6 — VISION & PHILOSOPHY (4 posts)

### 6.1 — Your AI agent can now build and manage websites on Wapka
MCP protocol. AI-native markdown docs. Use cases: non-tech users, developers, automation. The future of web tooling is AI-readable.

**Source**: `draft/wapka-5.txt` Part 5

### 6.2 — Why I open-sourced the platform
The decision. The fear. The outcome. Open source isn't a marketing tactic — it's insurance for the users and accountability for the builder.

**Source**: original reflection

### 6.3 — The responsibility of hosting other people's data for 10+ years
When someone builds their site on your platform, they trust you. That trust is heavier than code. Keeping data safe, accessible, and portable for a decade.

**Source**: `draft/wapka-history.txt` lines 26–28

### 6.4 — What's coming: the 2026–2027 roadmap
Native apps. Advanced Lua framework. Full OpenAPI REST. MCP protocol maturity. Self-hosting improvements. Where the platform is heading.

**Source**: `draft/wapka-history.txt` lines 30, `draft/wapka-5.txt`

---

## PART 7 — THE DEFINITIVE STATEMENT (1 post)

### 7.1 — Wapka: the complete platform review (9/10)
The anchor piece. Architecture. Freedom. Economics. AI-readiness. Verdict matrix. Who it's for. Who it isn't. The post you send when someone asks "what is Wapka?"

**Source**: `draft/wapka-5.txt` (full, condensed)

---

## Series at a glance

| Part | Posts | Theme |
|---|---|---|
| 1 | 6 | Founder's story |
| 2 | 6 | Technical architecture |
| 3 | 6 | Platform features |
| 4 | 4 | Open source & freedom |
| 5 | 5 | Positioning & audience |
| 6 | 4 | Vision & philosophy |
| 7 | 1 | Definitive review |
| **Total** | **32** | |

---

## Implementation checklist

### Infrastructure
- [ ] Add `Wapka` to category rules in `hugo.yaml`
- [ ] Update `docs/writing.md` + `docs/ai-instructions.md`
- [ ] Create `/content/wapka.md` — platform landing page
- [ ] Menu: `Posts · Wapka · Projects · Journal · Now · About`
- [ ] Create directory: `content/posts/wapka/`

### Posts
- [ ] Create all 32 posts as `draft: true` with full frontmatter
- [ ] Cross-link each post to 2–3 others in the series
- [ ] SEO-optimize every title + description + tags
- [ ] Source or create 1 image per post

### Publishing strategy
- [ ] Wave 1 (now): Part 1 (6 founder posts) + Part 2.1 (Lua)
- [ ] Wave 2 (week 2): Parts 2–3 (technical + features)
- [ ] Wave 3 (week 3): Parts 4–5 (freedom + positioning)
- [ ] Wave 4 (week 4): Parts 6–7 (vision + definitive review)

---

## Cross-linking map

```
Founder story (1.1–1.6)
  → Technical posts (2.1–2.6)     "Want the engineering? →"
  → Freedom posts (4.1–4.4)       "Want the philosophy? →"

Technical posts (2.1–2.6)
  → Feature posts (3.1–3.6)       "See it in action? →"
  → Comparisons (5.1)             "How it stacks up? →"

Feature posts (3.1–3.6)
  → Student post (5.3)            "Learning path? →"
  → AI post (6.1)                 "Future of this? →"

Freedom posts (4.1–4.4)
  → Comparison (5.1)              "Competitors? →"
  → Self-host guide (4.3)         "Try it yourself? →"

Positioning posts (5.1–5.5)
  → Definitive review (7.1)       "The verdict? →"

Vision posts (6.1–6.4)
  → Definitive review (7.1)       "The full picture? →"

Definitive review (7.1)
  → Links back to all 6 parts     "Deep dive any section."
```
