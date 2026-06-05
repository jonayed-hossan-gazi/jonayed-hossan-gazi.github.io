# Wapka Content Plan

A 10-post strategic content series to establish Wapka as a platform brand.
All posts are founder-authored by Jonayed Hossan Gazi.

---

## Tone principles

| Use | Avoid |
|---|---|
| "I started learning at 15" | "Kid from a poor country" |
| "Bootstrapped from zero" | "Third world, had nothing" |
| "Self-funded, reinvested every dollar" | "Couldn't afford servers" |
| "Saw an opportunity nobody was taking" | "Was sad when it shut down" |
| "Built regardless of circumstances" | "Impossible in my situation" |

Geography is texture, not the headline. The story is ambition, execution, and scale.

Every post should sound like a founder who built something significant — because he did.

---

## Post structure rules

- **1 clear message per post.** If a post has two messages, split it into two posts.
- **800–1500 words.** Long enough to be substantive, short enough to finish in one sitting.
- **Cross-link 2–3 other posts** in the series at the bottom: *"Continue reading: Why Lua? →"*
- **1 featured image per post** (Wapka screenshots, architecture diagrams, or abstract graphics).
- **SEO title tag**: 50–60 chars. **Meta description**: 120–155 chars. Both different from the H1.
- **Category**: `Wapka` for all 10 posts.
- **Tags**: specific to each post's topic + always include `wapka`.

---

## The 10 posts

### Post 1: I rebuilt a dead platform that 100,000 people now use

**Core message**: Vision + execution. 

A platform existed, served millions, then shut down. I saw the value everyone else abandoned. I decided to bring it back — not as nostalgia, but as a modern, competitive product.

**Key beats**:
- What Wapka was in its original form: a WAP site builder that gave anyone a free website
- When it shut down, the community scattered
- The insight: the need didn't go away — the product did
- The decision: rebuild it, modernized, open source, forever
- 100,000+ sites later, the bet paid off

**Source**: `draft/wapka-history.txt` lines 1–4, 19  
**SEO target**: "Wapka platform", "Wapka website builder", "what is Wapka"

---

### Post 2: From zero coding knowledge to shipping a platform

**Core message**: Focused work over time.

I didn't know how to code. I knew I needed to learn. 2 years of deliberate practice, prototype after prototype, failure after failure, until it shipped. This is not a talent story — it's a process story.

**Key beats**:
- 2017: starting point — basic HTML/CSS, nothing else
- 2018: first working prototype, crude but functional
- 2019: acquired wapka.co, wapka.site, wapka.website as domain alternatives
- 2020: finally secured wapka.org — the brand was unified
- What I learned about learning: you don't need to know everything. You need to know enough to ship.

**Source**: `draft/wapka-history.txt` lines 5–19  
**SEO target**: "learn to code and build a platform", "self-taught founder"

---

### Post 3: Why Lua? The architectural decision behind Wapka's scripting engine

**Core message**: Engineering confidence.

Choosing Lua wasn't a compromise. It was the deliberate, correct choice for a shared hosting platform that needed to run untrusted user code at zero marginal cost. Node and Python literally cannot do this economically.

**Key beats**:
- The problem: multi-tenant hosting where users can write server-side code
- The sandboxing requirement: you cannot let arbitrary code touch the system
- Lua's native sandboxing (`setfenv`, isolated states) makes this trivial
- LuaJIT runs at near-C speed with kilobyte memory footprints
- The free tier exists *because* Lua is this efficient — not despite it
- The Express-like framework makes it familiar to any web developer

**Source**: `draft/wapka-1.txt`, `draft/wapka-2.txt`  
**SEO target**: "why Lua for web development", "Lua sandbox hosting", "LuaJIT web framework"

---

### Post 4: A decade of code, zero forced migrations

**Core message**: Respect for the user.

WAP tags written in 2013, visual builder pages from 2018, Lua scripts from 2024, and REST APIs from 2026 — all run on the same data layer. Most platforms force you to migrate. Wapka evolves around you.

**Key beats**:
- The 3 eras of Wapka (WAP tags → visual builder → Lua + API)
- How the request router handles all three simultaneously
- Why backward compatibility is the hardest engineering problem no one appreciates
- The user never loses content, never needs to rebuild, never hears "deprecated"
- This is not technical debt — it's a design philosophy

**Source**: `draft/wapka-2.txt`, `draft/wapka-5.txt` (Part 3)  
**SEO target**: "backward compatibility web platform", "no migration website builder"

---

### Post 5: You can leave Wapka anytime — and that's why people stay

**Core message**: Freedom builds trust.

Open source on GitHub. Docker self-hosting. Raw database export. Detach your site, run it standalone, reattach later — no data loss. Most platforms build walls. Wapka built doors that open both ways.

**Key beats**:
- The detach/reattach cycle explained
- Raw DB export — your data, no proprietary format
- `docker compose up` — same software, same behavior, your server
- How this compares: Wix (0% portable), WordPress (painful export), Wapka (seamless)
- The paradox: giving users an exit makes them trust you enough to stay

**Source**: `draft/wapka-3.txt`, `draft/wapka-4.txt`  
**SEO target**: "open source website builder", "self-hosted CMS", "Docker web hosting platform"

---

### Post 6: 100GB free storage + server-side scripting for $0

**Core message**: Structural advantage.

The free tier isn't a loss leader. It's a consequence of Lua's efficiency. Every other platform burns money on compute. Wapka barely uses any. This is the economic moat.

**Key beats**:
- Resource comparison: Node/Python at scale vs Lua at scale
- Why a $5 VPS can't match 100GB storage
- Rate limits are honest — what you get and why
- The tradeoffs: shared compute on free tier, dedicated on paid
- The managed service value: CDN, SSL, DDoS protection, support — things self-hosters lose

**Source**: `draft/wapka-4.txt`, `draft/wapka-5.txt` (Part 8.3)  
**SEO target**: "free web hosting with scripting", "100GB free hosting", "free server-side coding"

---

### Post 7: Wapka vs WordPress vs Wix vs Vercel

**Core message**: Honest positioning.

Every platform has a strength. Knowing which one to use — and when not to use Wapka — is the point of this post.

**Key beats**:
- **vs Wix**: Wapka gives you server-side code; Wix doesn't
- **vs WordPress**: WordPress has the plugin ecosystem; Wapka has zero maintenance
- **vs Vercel**: Vercel is for frontend devs; Wapka is for full-stack with zero DevOps
- **vs Cloudron/Caprover**: Those host apps; Wapka builds them
- Who should NOT use Wapka (honest admission builds trust)
- Who Wapka is perfect for

**Source**: `draft/wapka-5.txt` (Part 7)  
**SEO target**: "Wapka vs WordPress", "Wapka vs Wix", "best website builder comparison"

---

### Post 8: Your AI agent can now build and manage websites on Wapka

**Core message**: Future-ready.

MCP (Model Context Protocol) support means AI models can read your site data, modify content, run Lua scripts, and manage files. The documentation is markdown-native — readable by both humans and models.

**Key beats**:
- What MCP is and why it matters
- How Wapka's markdown docs make it AI-native (vs PDF docs, video tutorials)
- Use cases: non-tech users ask AI to build features; developers automate workflows
- This isn't a gimmick — it's the direction web tooling is heading
- The platform is built for both human and autonomous use

**Source**: `draft/wapka-5.txt` (Part 5)  
**SEO target**: "AI web development MCP", "AI agent builds website", "Model Context Protocol web"

---

### Post 9: Between Wix and Vercel there's a void

**Core message**: Market positioning.

The web platform market is split. Beginners get locked into visual builders with no backend. Developers get serverless platforms with DevOps overhead. The middle ground — a platform that serves both and lets you grow without migrating — is empty. Wapka fills it.

**Key beats**:
- The two extremes of the market
- What falls through the cracks: people who want more than Wix but less than Vercel
- The upgrade path: visual builder → Lua scripting → REST API → self-hosting
- No migration at any stage. The same platform at every skill level.
- This gap exists because it's hard to solve. Wapka solved it.

**Source**: `draft/wapka-0.txt`, `draft/wapka-5.txt` (Part 1, 7)  
**SEO target**: "no-code to pro-code platform", "website builder for developers and beginners"

---

### Post 10: Wapka — the complete platform review (9/10)

**Core message**: The definitive statement.

The full, condensed argument. Architecture. Freedom. Economics. AI-readiness. Who it's for, who it's not for. This is the post you send someone who asks "what is Wapka?"

**Key beats**:
- What Wapka is (1 paragraph)
- The architecture (2 paragraphs)
- The open-source + self-host model (2 paragraphs)
- The AI integration (1 paragraph)
- The verdict matrix: concept 10/10, architecture 9/10, freedom 10/10, dev experience 7/10, lock-in risk 1/10
- Who should use it / who shouldn't
- The closing argument: Wapka isn't trying to be the biggest — it's trying to be the most free

**Source**: `draft/wapka-5.txt` (full document, condensed)  
**SEO target**: "Wapka review", "Wapka platform analysis", "best open source web platform"

---

## Implementation checklist

### New category
- [ ] Add `Wapka` to category rules in `hugo.yaml`
- [ ] Update `docs/writing.md` with new category
- [ ] Update `docs/ai-instructions.md` with new category

### Landing page
- [ ] Create `/content/wapka.md` — platform showcase with CTAs

### Menu
- [ ] Add Wapka to main menu: `Posts · Wapka · Projects · Journal · Now · About`

### Posts
- [ ] Create directory: `content/posts/wapka/`
- [ ] Create all 10 posts as `draft: true` with full frontmatter
- [ ] Cross-link each post to 2–3 others in the series
- [ ] SEO-optimize every title + description + tags
- [ ] Add 1 featured image per post (create placeholder or source from Wapka screenshots)

### Publishing strategy
- [ ] Publish posts 1–3 immediately (establish the brand)
- [ ] Publish posts 4–6 in week 2 (build technical credibility)
- [ ] Publish posts 7–9 in week 3 (comparisons + positioning)
- [ ] Publish post 10 as the definitive anchor piece

---

## Post interdependencies

```
Post 1 ──→ Post 2 (origin → build)
Post 3 ──→ Post 4 ──→ Post 5 ──→ Post 6 (technical arc)
Post 7 standalone, links to 3 4 5 6
Post 8 standalone, links to 3
Post 9 standalone, links to 1 5 7
Post 10 summarizes all, links to everything
```
