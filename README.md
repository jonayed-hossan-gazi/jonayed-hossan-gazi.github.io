# jonayed-hossan-gazi.github.io

My personal blog. Hugo + PaperMod on GitHub Pages.

## Philosophy

The simplest blog is just text files. No server, no database, no maintenance. Push to deploy.

## Structure

```
content/posts/     → blog posts, organized by category folder
content/           → about, projects, now, search (standalone pages)
static/images/     → all images live here, never hotlinked
layouts/           → only overrides I actually need
```

## Quick commands

```bash
hugo serve -D                           # preview with drafts
hugo new content posts/category/slug.md # new post from archetype
hugo --minify                           # build
```

[Writing posts](docs/writing.md) · [Deploy](docs/deploy.md) · [SEO](docs/seo.md) · [AI instructions](docs/ai-instructions.md)
