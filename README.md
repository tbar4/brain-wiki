# brain-wiki

A public digital garden built with [Quartz](https://quartz.jzhao.xyz/), exported from a private Obsidian vault.

This repo does not contain the vault itself — it contains only what the vault's owner explicitly opted in to publishing, via a per-file `publish: true` frontmatter key. The export pipeline lives in the private vault repo at `.brain/export-wiki.py`, gated by `meta/wiki-export-allowlist.txt` (which paths may ever be considered) and a per-file `publish: true` check (which files within those paths actually are). Quartz's own `explicit-publish` plugin re-checks the same flag a third time at build time, so a bug in the exporter alone can't leak a file onto the live site.

## What's here

- `content/wiki/` — topic hubs: hand-written argument above a marker, a nightly-regenerated index below it.
- `content/notes/permanent/` — the Zettelkasten permanent notes the hubs draw from and link into.

## Building

```sh
npm install
npx quartz build
```

Content is regenerated from the private vault by re-running the exporter there; this repo's `content/` directory is the output of that process, not hand-edited.
