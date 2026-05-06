# Environment setup

How to get this blog running on a fresh machine.

## Clone

```bash
git clone --recurse-submodules git@github.com:jonayed-hossan-gazi/jonayed-hossan-gazi.github.io.git
cd jonayed-hossan-gazi.github.io
```

The `--recurse-submodules` flag is critical — it pulls the PaperMod theme. Without it, `themes/PaperMod/` is empty.

## Install Hugo

```bash
# Linux (Ubuntu/Debian) — direct download
curl -sL "https://github.com/gohugoio/hugo/releases/download/v0.147.3/hugo_extended_0.147.3_linux-amd64.deb" -o /tmp/hugo.deb
sudo dpkg -i /tmp/hugo.deb

# macOS
brew install hugo

# Windows
choco install hugo-extended
```

**Must be the extended version** (SCSS support). Check the [releases page](https://github.com/gohugoio/hugo/releases) for the latest version.

Verify:

```bash
hugo version
# hugo v0.147.3+extended linux/amd64
```

## Run

```bash
hugo serve -D
```

Opens at `http://localhost:1313`. `-D` shows draft posts.

## Update

```bash
git pull --recurse-submodules
```
