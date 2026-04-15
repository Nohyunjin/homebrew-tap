# Nohyunjin/homebrew-tap

Homebrew formulae for [Nohyunjin](https://github.com/Nohyunjin)'s tools.

## Available formulae

- **[orgmem](Formula/orgmem.rb)** — agent-native knowledge & work graph.
  Markdown vault → SQLite + sqlite-vec, exposed to AI agents over MCP.
  Source: [Nohyunjin/orgmem](https://github.com/Nohyunjin/orgmem)

## Install

```bash
brew install Nohyunjin/tap/orgmem
```

(equivalent to `brew tap Nohyunjin/tap` followed by
`brew install orgmem`.)

### First run on macOS (ad-hoc signed binary)

From v0.1.1 the Mac binary is re-signed ad-hoc in CI via
`codesign --sign -`, so it runs on any arm64 Mac. If you installed
v0.1.0 (pre-codesign) and `kg` exits silently or with a "damaged app"
dialog, either re-sign locally…

```bash
codesign --force --sign - "$(which kg)"
```

…strip the quarantine flag…

```bash
xattr -d com.apple.quarantine "$(which kg)" 2>/dev/null || true
```

…or just upgrade: `brew upgrade orgmem`. Developer-ID notarization is
tracked for v0.2.

## How this tap is maintained

The Formula in this repo is a mirror — the source-of-truth lives at
[`packaging/homebrew/orgmem.rb`](https://github.com/Nohyunjin/orgmem/blob/main/packaging/homebrew/orgmem.rb)
in the orgmem repo, alongside a step-by-step
[release runbook](https://github.com/Nohyunjin/orgmem/blob/main/packaging/homebrew/README.md).
On every orgmem release the operator updates the upstream draft (version
+ url + sha256) and copies it into `Formula/` here.

If the Formula in this tap drifts from the upstream draft, the upstream
draft wins.

## License

Each formula references its upstream project's license. The Ruby files
in this repo are released under [MIT](LICENSE).
