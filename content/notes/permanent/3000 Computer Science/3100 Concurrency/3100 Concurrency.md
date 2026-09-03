---
stage: permanent
aliases:
  - Concurrency
  - 3100 Concurrency
created: 2026-02-09
tags:
  - concurrency
  - computer-networking
  - computer-to-computer
InZettelkasten: false
previousNote: "[[3000 Computer Science]]"
MoC:
category:
relatedNotes:
distilled: false
publish: true
---
---
# 3100 Concurrency

---

```base
properties:
  file.name:
    displayName: Child Notes
views:
  - type: table
    name: Child Notes
    filters:
      and:
        - file.folder.startsWith("001 Zettelkasten/")
        - list(previousNote).contains(this)
    order:
      - file.name
      - created
    sort:
      - property: InZettelkasten
        direction: ASC
      - property: file.name
        direction: ASC

```

```base
properties:
  file.name:
    displayName: Related Notes
views:
  - type: table
    name: Related Notes
    filters:
      and:
        - file.folder.startsWith("001 Zettelkasten/")
        - list(realtedNotes).contains(this)
    order:
      - file.name
      - created
    sort:
      - property: file.name
        direction: ASC

```
