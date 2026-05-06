# Deploy

Push to `main`. Everything else is automatic.

## How it works

`.github/workflows/deploy.yml` runs on every push. It builds Hugo and pushes `/public/` to the `gh-pages` branch. GitHub serves from there.

## Live URL

`https://jonayed-hossan-gazi.github.io`

## Custom domain

When ready:

1. Add CNAME: `echo "jonayed.dev" > static/CNAME`
2. Update `baseURL` in `hugo.yaml`
3. DNS: CNAME record pointing to `jonayed-hossan-gazi.github.io`
4. Settings → Pages → Enforce HTTPS

## Build locally

```bash
hugo --minify      # production
hugo serve -D       # development with drafts
```
