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
# macOS
brew install hugo

# Linux (snap)
sudo snap install hugo --channel=extended

# Linux (apt — may be outdated)
sudo apt install hugo

# Windows
choco install hugo-extended
```

Verify:

```bash
hugo version
# hugo v0.147.3+extended linux/amd64
```

Must say `extended`. Required for SCSS support.

## Run

```bash
hugo serve -D
```

Opens at `http://localhost:1313`. `-D` shows draft posts.

## Update

```bash
git pull --recurse-submodules
```
