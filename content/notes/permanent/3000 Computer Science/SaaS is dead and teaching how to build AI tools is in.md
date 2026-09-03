---
stage: permanent
aliases:
  - SaaS is dead and teaching how to build AI tools is in
created: 2026-02-09
MoC: ai
category: technology
tags:
  - ai
  - technology
previousNote:
relatedNotes:
  - "[[3100 Concurrency]]"
InZettelkasten: false
distilled: false
publish: true
---
---
It starts to make less and less sense to pay an exhorbanant amount of money to a SaaS company when a Claude subscription is much cheaper. Software will shift to serve other AI integrations, meaning that software development will be used to serve AIs referencing other AIs.

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
