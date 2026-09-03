---
type: hub
tier: growing
state: budding
publish: true
created: 2026-09-03
---

# AI and Reasoning Systems

*growing · 16 principles*

## What this hub is

Sixteen engineering records promoted out of `contexts/**/decisions/`, split
almost evenly between two projects that never talked to each other: the
Panoptes SDA-evaluation design inside the thesis (`contexts/school`,
archived — the thesis was torn down and is being rebuilt from scratch) and
the agent-tooling work behind this brain and thesis-app itself
(`contexts/tooling`, live). The thesis records are stamped `superseded` —
Trevor reset the whole design on 2026-08-26 — but the note attached to nearly
every one of them says the same thing: *the reasoning survives the reset, and
a rebuilt design will meet these questions again.* Read them as methodology,
not as an active plan.

**The thread connecting both halves is stated outright in
[[contexts/career/decisions/ai-eval-engineering-target-role|ai-eval-engineering-target-role]]:**
harness craft is the abundant skill and is ranked last on purpose; small-sample
statistical inference — knowing whether a measured delta is real, and how much
of it is item difficulty versus judge noise — is the scarce one. Almost every
other record here is that principle showing up as a specific, costly instance.

**A threshold or a signal is only worth what the corpus does with it, not
what the reasoning behind it sounds like.**
[[contexts/school/decisions/closure-detection-has-no-signal-in-this-corpus|closure-detection-has-no-signal-in-this-corpus]]
approved a design, then killed it hours later by running it against the real
28 open threads and finding it selected 75% of the corpus and ranked the
genuinely stale items *below* the live ones — the fourth time in this vault a
threshold reasoned about in advance failed against the data it had to run on.
[[contexts/school/decisions/claude-code-backend-measured-and-rejected|claude-code-backend-measured-and-rejected]]
is the same move on a bigger design: a whole host-socket integration for a
"missing" cloud backend was scrapped in minutes once someone actually queried
the running container and found the slot was already filled and already
faster.

**The eval-methodology cluster is about designing contamination and bias out
rather than measuring them after the fact.**
[[contexts/school/decisions/benchmark-contamination-control|benchmark-contamination-control]]
and
[[contexts/school/decisions/hindsight-contamination-and-as-of-construction|hindsight-contamination-and-as-of-construction]]
split "the model has seen this" from "the vignette encodes facts unknowable
at the decision point," and note the second is invisible to any canary — it
just reads as a well-built benchmark.
[[contexts/school/decisions/final-model-list-and-api-budget|final-model-list-and-api-budget]]
keeps a frontier model as a calibration *anchor* rather than the judge,
because promoting it would silently delete the inter-rater statistic the
judge panel exists to produce, and excludes the policy model's own family
from judging it, rather than measuring the self-preference bias afterward.
[[contexts/school/decisions/second-coder-dropped-replacement-validity|second-coder-dropped-replacement-validity]]
and
[[contexts/school/decisions/kl-coefficient-and-reference-policy|kl-coefficient-and-reference-policy]]
are both about naming a methodological limit precisely (stability, not
reproducibility; KL as an ablation axis a LoRA setup gets for free) instead of
either hiding it or overbuilding around it — the same restraint as
[[contexts/school/decisions/harness-ladder-discipline-or-open-build|harness-ladder-discipline-or-open-build]]
and
[[contexts/school/decisions/thesis-hardware-envelope|thesis-hardware-envelope]],
which both turn a hard constraint (no harness, 16GB of VRAM) into an argued
design choice rather than an apology.

**The agent-tooling cluster is the same discipline applied to running agents
rather than to evaluating them**, and it keeps finding that the interactive
check lied. [[contexts/tooling/decisions/find-is-shimmed-in-claude-sessions|find-is-shimmed-in-claude-sessions]]
and
[[contexts/tooling/decisions/concurrent-sessions-one-working-tree|concurrent-sessions-one-working-tree]]
both trace a "broken" guard back to a shell function silently substituting a
different binary under interactive use than under cron.
[[contexts/tooling/decisions/a-handoff-can-be-stale-about-the-stack|a-handoff-can-be-stale-about-the-stack]]
generalizes it to design documents themselves: every file path a stale
handoff named still existed on disk, which is what made it dangerous rather
than obviously wrong.
[[contexts/tooling/decisions/adversarial-review-is-a-command|adversarial-review-is-a-command]]
measured a multi-agent review process the same way — location beats
reasoning (every fatal finding was something the author had not opened) and a
two-value verdict schema hides that a "refutation" stage refuted nothing.
[[contexts/tooling/decisions/atlas-is-agent-written-never-published|atlas-is-agent-written-never-published]]
and
[[contexts/tooling/decisions/autobrain-commits-only-derived-output|autobrain-commits-only-derived-output]]
round the cluster out with the same structural-not-conventional argument as
the security hub: an unattended job may commit only what it can regenerate,
and agent authorship is bounded by a folder rather than a review gate,
because a per-item sign-off is exactly the gate that already let AI-drafted
prose through once.

<!-- GENERATED — everything below is rewritten nightly, do not edit -->
## Notes (0)

Nothing in the corpus matches this cluster yet.

## Engineering lessons (16)

- [[contexts/tooling/decisions/a-handoff-can-be-stale-about-the-stack|A spec naming a path that exists but is no longer served fails silently and completely]]
- [[contexts/tooling/decisions/adversarial-review-is-a-command|In multi-agent review, location beats reasoning — and a two-value verdict schema hides that nothing was refuted]]
- [[contexts/career/decisions/ai-eval-engineering-target-role|In AI evaluation, small-sample inference is the scarce skill and harness craft is the abundant one]]
- [[contexts/tooling/decisions/atlas-is-agent-written-never-published|Make the violation structurally impossible, because a per-item sign-off gate is what let the last one through]]
- [[contexts/tooling/decisions/autobrain-commits-only-derived-output|An unattended job may commit only what it can regenerate]]
- [[contexts/school/decisions/benchmark-contamination-control|Canaries and held-out splits cannot be added retroactively — and a canary detects contamination without curing it]]
- [[contexts/school/decisions/claude-code-backend-measured-and-rejected|A record about deployed configuration decays — check the deployment, not the record]]
- [[contexts/school/decisions/closure-detection-has-no-signal-in-this-corpus|A signal that selects three quarters of the corpus is a prior, not a filter]]
- [[contexts/tooling/decisions/concurrent-sessions-one-working-tree|Parallel agent sessions need four isolations, and the shared working tree is one of the lanes]]
- [[contexts/school/decisions/final-model-list-and-api-budget|A single judge has no inter-rater statistic — design the self-preference bias out rather than measure it]]
- [[contexts/tooling/decisions/find-is-shimmed-in-claude-sessions|Your interactive shell may not resolve the same binaries production does]]
- [[contexts/school/decisions/harness-ladder-discipline-or-open-build|Make the metric and the reward literally one function, and do not build a harness]]
- [[contexts/school/decisions/hindsight-contamination-and-as-of-construction|Hindsight contamination is a second axis, and no harness can flag it]]
- [[contexts/school/decisions/kl-coefficient-and-reference-policy|With LoRA the reference policy is free, so KL becomes an ablation axis rather than a constant]]
- [[contexts/school/decisions/second-coder-dropped-replacement-validity|A judge panel that agrees with itself proves shared priors as easily as a good codebook]]
- [[contexts/school/decisions/thesis-hardware-envelope|At fixed wall-clock a smaller policy buys more seeds and ablations than parameter count]]

## Recently added (0)

Nothing yet.

## Gaps detected

None detected.

*Generated 2026-09-03 by `.brain/wiki-build.py`. Everything above the marker is hand-written; everything below it is not. A stale readout says so on its face.*
