# openclaw-patches

Git patches for [OpenClaw](https://github.com/openclaw/openclaw). Apply to source, build, install.

## Patches

| # | Type | Description |
|---|------|-------------|
| 0001 | fix | Inject messageId from toolContext for react actions (#17651) |
| 0002 | fix | Preserve group context from non-allowlisted senders |
| 0003 | feat | Enable block streaming and tool summaries for WhatsApp |

## Usage

### Apply patches to source

```bash
git clone https://github.com/openclaw/openclaw.git
cd openclaw

# Apply all
git am ../openclaw-patches/patches/*.patch

# Apply specific
git am ../openclaw-patches/patches/0001-*.patch
```

### Build and install

```bash
npm install
npm run build
npm install -g .
openclaw gateway restart
```

### After upstream update

```bash
cd openclaw
git fetch origin
git rebase origin/main
# Resolve conflicts if any
```

## Notes

- Generated with `git format-patch` against OpenClaw `main` branch
- Tested on version `2026.2.27` (commit `62387b8`)
- Author: Breno (`bghaesee@outlook.com`), Co-author: Lis (`lis@hanake0.dev`)
