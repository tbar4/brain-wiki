---
type: hub
tier: evergreen
state: evergreen
tags: [rust, concurrency]
publish: true
created: 2026-09-02
updated: 2026-09-02
---

# Rust and Systems Programming

*Draft header — written from the corpus, awaiting Trevor's revision.*

*evergreen · 7 notes · one book, read to page 20*

## What this corpus argues

Three notes carry content and all three come from
[[notes/literature/Rust Atomics and Locks|Rust Atomics and Locks]] (Mara Bos),
pages 16, 18 and 20 — the opening of chapter one.
[[3101.1 Operating Systems isolate processes from each other]] sets the premise:
the kernel isolates processes, threads within one process share memory and
resources, and every Rust program starts with a main thread that can `spawn`
more. The other two are its consequences —
[[3101.1-b Spawned Threads May not finish executing before the main thread]]
takes `join()` and handles as the way to wait, and
[[3101.1-a It is more common to pass closures to threads]] takes `move` and the
`'static` bound as the way to hand a value to a thread that may outlive its
caller. [[0106.7-a Defense Tech moving to Rust]] is the only note here that
argues rather than explains, and its subject is procurement rather than
concurrency: DARPA uses Rust, defence technology is downstream of DARPA, so the
choice is Rust over the memory unsafety of C and C++ and over falling back to
Python.

**Where the corpus disagrees:** it cannot. One book, one author, three notes.

**Gap:** effectively everything. [[3000 Computer Science]],
[[3100 Concurrency]] and [[3101 Concurrency in Rust]] are empty — a heading
apiece and no sentence. The source carries 102 highlights and three became
notes; nothing here covers ownership, borrowing, lifetimes beyond the single
`'static` mention, `async`, `unsafe`, or the atomics and locks the book is named
for. The clearest signal of where this branch is going is not a permanent note
at all: [[mini-lsm-schedule|Mini-LSM Schedule]], fleeting, dated 2026-09-01,
plans three weeks building an LSM storage engine in Rust — memtables, SSTs,
compaction, WAL, MVCC. None of it has reached the slip box yet.

<!-- GENERATED — everything below is rewritten nightly, do not edit -->
## Notes (7)

**3000 Computer Science** (6)

- [[3000 Computer Science]]
- [[3100 Concurrency]]
- [[3101 Concurrency in Rust]]
- [[3101.1 Operating Systems isolate processes from each other]]
- [[3101.1-a It is more common to pass closures to threads]]
- [[3101.1-b Spawned Threads May not finish executing before the main thread]]

**0000 Military Sciences** (1)

- [[0106.7-a Defense Tech moving to Rust]]

## Engineering lessons (1)

- [[contexts/business/projects/ontology-engine/decisions/postgres-stays|"Write it yourself" stops at the storage engine — and the port belongs at the I/O boundary, not with the domain]]

## Recently added

No usable recency signal. 7 of 7 notes in this hub share one file date (2026-09-03, a bulk frontmatter rewrite), and `created:` is absent from most of the corpus. Recency here would be an artefact of a tool run, not of when anything was written.

## Gaps detected

- **0000 Military Sciences is touched once** — one note, so the cluster reaches into it without arguing there.

*Generated 2026-09-03 by `.brain/wiki-build.py`. Everything above the marker is hand-written; everything below it is not. A stale readout says so on its face.*
