# SEO

Everything is baked in. No plugins.

## What's auto-generated

- Sitemap: `/sitemap.xml`
- Robots: `/robots.txt`
- RSS: `/index.xml` + per-category feeds
- OpenGraph tags: title, description, image, type
- Twitter Cards: `summary_large_image` with image
- JSON-LD: BlogPosting + BreadcrumbList on every post
- Canonical URLs
- Meta description and keywords

## What I added manually

- Person JSON-LD schema on homepage (extends PaperMod head)
- `twitter:site` and `twitter:creator` tags
- Default OG image: `/images/site/og-default.png`
- `humans.txt`
- Custom 404 page with links

## Google Search Console

1. Go to [search.google.com/search-console](https://search.google.com/search-console)
2. Add property: `jonayed-hossan-gazi.github.io`
3. Get the verification meta tag
4. Paste in `hugo.yaml` → `params.googleSiteVerification`
5. Push. Deploy. Done.

## Verify

- [Schema validator](https://validator.schema.org)
- [Rich Results Test](https://search.google.com/test/rich-results)
- [OG debugger](https://www.opengraph.xyz)
- [PageSpeed Insights](https://pagespeed.web.dev)
