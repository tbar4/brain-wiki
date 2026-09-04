---
type: hub
tier: evergreen
state: evergreen
tags: [knowledge-management, note-taking]
publish: true
created: 2026-09-02
updated: 2026-09-02
---

# Knowledge Management

*Draft header — written from the corpus, awaiting Trevor's revision.*

*evergreen · 59 notes · branch 4000 in full, flat, no sub-folders*

## What this corpus argues

Two books hold the branch and they answer different questions. Tiago Forte's
*Building a Second Brain* and *The PARA Method* occupy 4001 and ask where a note
goes: [[4001.1 The PARA Method]] sorts by the reader's present relationship to a
thing rather than by its subject — *"there is no 'correct' place to put an item
in PARA"* — and [[4001.2.4 Organize your notes for action]] makes actionability
the sorting key outright. Sönke Ahrens's *How to Take Smart Notes* holds
everything from 4002 to 4006 and asks what a note is for.
[[4002.1 External Structure for Thinking]] argues that thinking needs a structure
outside the head and that the structure is writing;
[[4003 Thinking and Writing]] quotes Luhmann's *"one cannot think without
writing"* and denies that writing follows research at all.

Where they touch, they touch on one instruction: put it in your own words.
[[4001.2.1 Write Notes in Your Own Words]] and
[[4004.2 Rewrite notes in your own words]] are near-identical claims taken from
different books, and neither cites the other.

Their filing rules are not obviously compatible.
[[4004.1 How to develop Insight]] holds that arguments must be built bottom-up
and that *"creating artificial hierarchies only creates frustration"*, and
[[4006.3 Note References]] says to link note to note rather than note to index,
while PARA is four folders maintained by hand. The branch is itself written in
the notation [[4006.2 Taking Permanent Notes]] sets out — numbers for facts in
your own words, letters for your own interpretation. The corpus registers the
tension once and resolves it by addition:
[[4003.3 Success in Academic Writing]] lists PARA, CODE and Zettelkasten together
as systems that *"have helped many become successful writers."*

**Where the corpus disagrees:** it does not. The one note that names both systems
joins them. No note asks whether a second brain works or what it costs, and no
sceptical source appears anywhere in the 59 — every claim here is a method's own
account of itself.

**Gap:** the corpus cannot check its main source. Ahrens is cited by 31 of these
notes, always as a bare `[[How to Take Smart Notes]]` with no page or line, while
4001 cites Forte to the page through a thirty-item reference list with block
anchors in [[4001 Building Your Second Brain]]. The Ahrens literature note has an
empty *What I take from it* and a *Raw material* section of 46 embeds that
resolve to nothing. And Luhmann, whose scheme 4006.2 reconstructs in detail,
exists in this vault as one quoted sentence — no work of his is in `sources/` at
all.

<!-- GENERATED — everything below is rewritten nightly, do not edit -->
## Notes (59)

**4000 Knowledge Management** (59)

- [[4000 Knowledge Management]]
- [[4001 Building Your Second Brain]]
- [[4001.1 The PARA Method]]
- [[4001.1.1 Projects]]
- [[4001.1.1.1 The Biggest Highlighting Mistakes]]
- [[4001.1.1.1 Touch Lightly, Move Quickly]]
- [[4001.1.1.2 Project Kickoff Checklist]]
- [[4001.1.1.3 Dial down the scope]]
- [[4001.1.1.4 Create project completion checklist]]
- [[4001.1.1.5 Making Projects Manageable]]
- [[4001.1.2 Areas]]
- [[4001.1.3 Resources]]
- [[4001.1.4 Archives]]
- [[4001.2 The CODE Method]]
- [[4001.2.1 Write Notes in Your Own Words]]
- [[4001.2.1.1 Progressive Summarization Technique]]
- [[4001.2.2 Only Capture Ideas That Resonate with You]]
- [[4001.2.3 3 Important Note Taking Habits]]
- [[4001.2.4 Organize your notes for action]]
- [[4001.2.5 Create an Archipelago of Ideas]]
- [[4001.2.6 Divergence-Convergence Process]]
- [[4002 Creating Structure]]
- [[4002.1 External Structure for Thinking]]
- [[4002.1.1 Procrastination]]
- [[4002.2 Adding to your Slip Box]]
- [[4002.4 Defining Tasks]]
- [[4003 Thinking and Writing]]
- [[4003-a Intelligence is a last resort for mankind]]
- [[4003.1 Writing is the Medium of Research]]
- [[4003.2 Quality of Writing]]
- [[4003.3 Success in Academic Writing]]
- [[4003.4 Ordering our Thoughts]]
- [[4003.5 Becoming more engaged in reading]]
- [[4003.6 Remembering for the Long Run]]
- [[4003.7 Information isn't a luxury, it is a key to survival]]
- [[4003.8 Be a Note Giver, Not Taker]]
- [[4004 Generating Insight]]
- [[4004.1 How to develop Insight]]
- [[4004.2 Rewrite notes in your own words]]
- [[4004.3 Atomic Notes]]
- [[4004.4 Simplicity of ideas]]
- [[4005 How to Learn]]
- [[4005.1 Need to test ourselves to verify understanding]]
- [[4005.10 Connect to as many useful contexts as possible]]
- [[4005.2 Elaboration]]
- [[4005.3 Think beyond the text]]
- [[4005.4 Read with Questions in mind]]
- [[4005.5 Let Experience be the Guide]]
- [[4005.6 Use your Intuition]]
- [[4005.7 Intelligence vs Self Control]]
- [[4005.8 Planners vs Experts]]
- [[4005.9 Success stems from smart working environments]]
- [[4006 Zettelkasten]]
- [[4006.1 Taking Literature Notes]]
- [[4006.2 Taking Permanent Notes]]
- [[4006.2.1 Permanent Notes as Thinking]]
- [[4006.3 Note References]]
- [[4006.4 Good Keywords]]
- [[4006.5 Overview Links]]

## Engineering lessons (18)

- [[contexts/school/decisions/a-context-is-tags-plus-sources|A filter with no rules must select nothing, not everything]]
- [[contexts/school/decisions/a-link-reason-is-required-only-where-it-is-asserted|Require a link's reason only where a human asserts the link]]
- [[contexts/projects/thesis-app/decisions/a-reader-highlight-is-not-a-source|A reader highlight is not a source, and counting it as one inflates the library]]
- [[contexts/tooling/decisions/a-skill-reaches-four-harnesses-a-command-reaches-one|Author capability as a skill: a skill reaches four harnesses, a command reaches one]]
- [[contexts/projects/thesis-app/decisions/board-arrangement-and-corpus-claims-are-two-edge-kinds|Layout adjacency and an asserted claim are two edge kinds, and merging them is a one-way door]]
- [[contexts/tooling/decisions/closed-threads-orphan-their-citations|Threads close in place, because deleting one orphans every citation into it]]
- [[contexts/school/decisions/context-lens-splits-by-choice-not-by-subject|Two activities on one subject cannot be separated by a subject-derived taxonomy]]
- [[contexts/tooling/decisions/decide-in-obsidian-file-in-claude|Decide in the reading surface, file in the writing one]]
- [[contexts/tooling/decisions/essays-ripen-they-are-not-scheduled|The trigger is the only designable part of a writing practice — rank by ripeness, never by a calendar]]
- [[contexts/tooling/decisions/para-not-adopted|Organise by actionability for a human browser and by topic for a model reader]]
- [[contexts/tooling/decisions/permanent-notes-distil-into-mocs|`distilled` is a consumption flag, not a quality grade]]
- [[contexts/projects/thesis-app/decisions/the-corpus-is-unlinked-not-the-design-wrong|When retrieval returns nothing, suspect the corpus before the design]]
- [[contexts/school/decisions/thesis-app-design-philosophy|Organise a knowledge system around the acts a person performs, not the tables it stores]]
- [[contexts/projects/thesis-app/decisions/thesis-app-has-no-folders-and-the-zettel-id-is-the-tree|The id is the tree; folders are only a rendering of it]]
- [[contexts/tooling/decisions/vault-folders-by-pipeline-stage|Only one axis can be folders: pick the one that encodes a rule folders can enforce]]
- [[contexts/school/decisions/writing-proposals-cross-domain-bridge|A disjointness test punishes accurate tagging: better metadata strangles the detector]]
- [[contexts/projects/thesis-app/decisions/zettel-ids-live-in-a-column-not-the-title|The Luhmann id lives in a column, never in the title]]
- [[contexts/projects/thesis-app/decisions/zettelkasten-ladder-adds-moc|Maps of Content complete the ladder, and distil is the operation at every rung]]

## Recently added

No usable recency signal. 59 of 59 notes in this hub share one file date (2026-09-03, a bulk frontmatter rewrite), and `created:` is absent from most of the corpus. Recency here would be an artefact of a tool run, not of when anything was written.

## Gaps detected

None detected.

*Generated 2026-09-03 by `.brain/wiki-build.py`. Everything above the marker is hand-written; everything below it is not. A stale readout says so on its face.*
