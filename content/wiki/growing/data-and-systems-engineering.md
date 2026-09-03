---
type: hub
tier: growing
state: budding
publish: true
created: 2026-09-03
---

# Data and Systems Engineering

*growing · 55 principles*

## What this hub is

Fifty-five engineering records — the largest and most heterogeneous of the
three growing hubs, merged from what were originally five narrower
categories (systems design, ops, data pipelines, debugging/verification,
database internals) because none cleared eight members alone. They come
from five different projects: this vault's own tooling and the archived
thesis-app dominate by volume, with the archived data-platform (a
dbt/Airflow/Cube warehouse) and the archived ontology-engine (a Rust
bitemporal assertion log) supplying the sharpest database-internals
material, plus a handful from live homelab infrastructure. Read a sample
across projects and the 55 sort into a few real clusters rather than one
theory.

**Checks that pass while the thing they check is wrong** is the largest
cluster by a wide margin.
[[contexts/tooling/decisions/a-check-must-observe-the-artifact|A check must observe the artifact, not a proxy for it]]
names it directly and catalogues six instances from one day of work alone;
the same shape recurs independently across every project in this hub.
[[contexts/business/projects/data-platform/decisions/stale-but-green|stale-but-green]]
generalizes it for derived data specifically — *"a derived artifact's health
signals describe its machinery, never its correctness"* — so a Cube rollup
can report every green signal while serving numbers three weeks stale,
because the check that would catch it has to compare the artifact against
its source and nothing inside the artifact can do that.
[[contexts/tooling/decisions/an-empty-result-is-not-an-absent-source|an-empty-result-is-not-an-absent-source]]
is the same failure at the predicate level — thesis-app conflated "no rows"
with "not mounted," and the fallback it triggered was armed by
*correctness*, not by a bug, pushing eleven retired calendar events onto a
live Google account.
[[contexts/school/decisions/a-cascade-delete-is-invisible-to-the-sync-layer|a-cascade-delete-is-invisible-to-the-sync-layer]],
[[contexts/school/decisions/the-in-app-backup-task-still-writes-zero-bytes|the-in-app-backup-task-still-writes-zero-bytes]]
and
[[contexts/school/decisions/a-call-needs-a-horizon|a-call-needs-a-horizon]]
("the guard was in the comment, not the code") are further instances — a
cascade delete with no remote counterpart, a directory of correctly-named
zero-byte backups, and a deadline rule stated correctly two lines above the
code that didn't apply it.

**Deploys and jobs that leave the next run to discover the damage** is the
second cluster.
[[contexts/school/decisions/branch-deploys-diverge-the-prod-schema|branch-deploys-diverge-the-prod-schema]]
and
[[contexts/school/decisions/an-interrupted-compose-up-breaks-the-next-deploy|an-interrupted-compose-up-breaks-the-next-deploy]]
both show a deploy that reports success while quietly moving state one step
ahead of the code that has to run against it — and the failure then lands on
a *later*, unrelated deploy, which is what makes it hard to attribute.
[[contexts/business/projects/data-platform/decisions/dlt-commits-state-at-load|dlt-commits-state-at-load]]
is the pipeline version: a rate-limited source that fails mid-extract loses
every checkpoint it hadn't yet committed, because state commits at load, not
as work happens.
[[contexts/tooling/decisions/lock-owner-bypasses-the-commit-hook|lock-owner-bypasses-the-commit-hook]]
is the inverse problem — a guard built to protect a shared resource has to
explicitly let its own owner through, or it deadlocks the one process it
exists to protect.

**Two things that should be one, or one thing mistaken for two** rounds out
what was sampled. `/data` mounted twice looks like two filesystems to a
container and silently defeats hardlinking
([[contexts/homelab/decisions/arr-stack-single-data-mount|arr-stack-single-data-mount]]);
a firewall and a Docker-published port answer to different iptables chains
entirely, so enabling ufw closes nothing
([[contexts/homelab/decisions/a-published-docker-port-is-not-closed-by-ufw|a-published-docker-port-is-not-closed-by-ufw]]);
and overlapping assertions from two sources about the same object are not a
data-quality bug to resolve but the entire point of a bitemporal log, so
"current state" has to be a resolution policy rather than a uniqueness
constraint
([[contexts/business/projects/ontology-engine/decisions/current-state-is-a-resolution-policy|current-state-is-a-resolution-policy]],
[[contexts/business/projects/ontology-engine/decisions/assertion-log-is-the-core|assertion-log-is-the-core]],
[[contexts/business/projects/ontology-engine/decisions/assertion-granularity-equals-correction-granularity|assertion-granularity-equals-correction-granularity]]).
The rest of the ontology-engine and data-platform material —
[[contexts/business/projects/data-platform/decisions/airflow-metadata-as-a-source|airflow-metadata-as-a-source]],
[[contexts/business/projects/data-platform/decisions/window-not-offset-pagination|window-not-offset-pagination]],
[[contexts/business/projects/data-platform/decisions/cube-pre-aggregations|cube-pre-aggregations]] —
is warehouse-specific engineering rather than a cross-project pattern, and is
better read directly than summarized here.

Roughly a third of the 55 come from projects that are archived — the
ontology-engine's TAP Lab bid was not selected, and the thesis was torn down
and is being rebuilt from scratch. Nothing above stopped being true when
either project ended; only the machine it was learned on did.

<!-- GENERATED — everything below is rewritten nightly, do not edit -->
## Notes (0)

Nothing in the corpus matches this cluster yet.

## Engineering lessons (55)

- [[contexts/school/decisions/a-board-edge-is-not-a-claim|A layout edge and an asserted claim are two kinds of line and must not share a table]]
- [[contexts/school/decisions/a-call-needs-a-horizon|The guard was in the comment, not the code — and two clocks in one predicate go red at midnight]]
- [[contexts/school/decisions/a-cascade-delete-is-invisible-to-the-sync-layer|A cascade delete is invisible to the sync layer, so the remote copy outlives the local one]]
- [[contexts/tooling/decisions/a-check-must-observe-the-artifact|A check must observe the artifact, not a proxy for it]]
- [[contexts/school/decisions/a-finished-component-nothing-renders|Capability can be complete and still have no way in]]
- [[contexts/school/decisions/a-fixture-cannot-find-what-only-the-corpus-has|A fixture cannot find what only the corpus has]]
- [[contexts/school/decisions/a-fixture-that-cannot-fail-is-not-a-test|A fixture that cannot produce the real case is not a test]]
- [[contexts/homelab/decisions/a-published-docker-port-is-not-closed-by-ufw|A published Docker port is not closed by a firewall — close it by not publishing it]]
- [[contexts/business/projects/data-platform/decisions/airflow-metadata-as-a-source|Ingest an orchestrator's metadata with an allowlist, and count rows from the loader, not the scheduler]]
- [[contexts/tooling/decisions/an-empty-result-is-not-an-absent-source|An empty result is not an absent source, and the fallback that conflates them is armed by correctness]]
- [[contexts/school/decisions/an-interrupted-compose-up-breaks-the-next-deploy|An interrupted `docker compose up` takes production down on the *next* deploy]]
- [[contexts/business/projects/data-platform/decisions/api-window-width-is-the-failure-mode|A wide request window is the failure, not a flaky upstream]]
- [[contexts/homelab/decisions/arr-stack-single-data-mount|Two bind mounts of one filesystem are two filesystems to the container, and hardlinking degrades to copying in silence]]
- [[contexts/business/projects/ontology-engine/decisions/assertion-granularity-equals-correction-granularity|Assertion granularity must equal correction granularity]]
- [[contexts/business/projects/ontology-engine/decisions/assertion-log-is-the-core|The atomic unit is an append-only bitemporal assertion, not a table row]]
- [[contexts/school/decisions/autosave-cancelled-what-it-should-have-flushed|A debounced autosave must flush on unmount, or it cancels the save it owed]]
- [[contexts/school/decisions/branch-deploys-diverge-the-prod-schema|A branch deploy can move the production schema past every branch that can serve it]]
- [[contexts/business/projects/data-platform/decisions/conjunction-pc-is-estimated-not-authoritative|An estimate must carry its epistemic status in its column name, all the way downstream]]
- [[contexts/business/projects/data-platform/decisions/conjunction-screen-silent-failures|A capped run is a sample, not a screen — and nothing downstream can tell the difference]]
- [[contexts/business/projects/data-platform/decisions/covariance-history-must-be-age-bounded|When a statistic compares model outputs to each other, find out what actually drives the spread]]
- [[contexts/business/projects/data-platform/decisions/cube-pre-aggregations|Only additive measures survive a rollup, and a query cache hides whether the rollup was used]]
- [[contexts/business/projects/ontology-engine/decisions/current-state-is-a-resolution-policy|If overlapping assertions are legal, "current state" is a policy, not a constraint]]
- [[contexts/business/projects/data-platform/decisions/dlt-commits-state-at-load|A rate-limited source must load in batches, because incremental state commits at load]]
- [[contexts/business/projects/data-platform/decisions/dlt-variant-columns|Type inference forks a column silently, which is worse than failing]]
- [[contexts/school/decisions/drawn-where-you-cannot-click-it|A flex child cannot cover its parent's padding, and one-axis scrolling clips the other]]
- [[contexts/homelab/decisions/drm-render-nodes-move-across-reboots|Never name a device node that is enumerated at boot — address it by bus path]]
- [[contexts/homelab/decisions/gh-cannot-reach-the-keyring-headless|A headless tool shell hangs on a keyring, it does not fail]]
- [[contexts/tooling/decisions/lock-owner-bypasses-the-commit-hook|A lock-checking hook must exempt the lock's owner, or it deadlocks the holder]]
- [[contexts/business/projects/data-platform/decisions/multi-endpoint-apis-are-one-source|An API with many endpoints is one source, not many pipelines]]
- [[contexts/business/projects/ontology-engine/decisions/parallel-not-cutover|A parallel rewrite must not read from the system it is replacing]]
- [[contexts/school/decisions/placement-and-orphans-are-one-rule|Two independent implementations of one rule agree until they don't, and the disagreement is invisible]]
- [[contexts/school/decisions/prod-compose-merges-a-stale-worktree|A compose project can be assembled from two files, and production's data can live inside a git worktree]]
- [[contexts/homelab/decisions/prod-env-lives-in-the-deploy-worktree|Compose reads its environment file beside the compose file, and a rotated secret needs a recreate, not a restart]]
- [[contexts/school/decisions/proxy-timeout-is-the-model-call-ceiling|The reverse proxy, not the model, sets the ceiling on every model call]]
- [[contexts/school/decisions/removing-chrome-is-not-removing-routes|Removing navigation chrome is a claim about the replacement, not about the routes]]
- [[contexts/business/projects/data-platform/decisions/retry-belongs-at-the-orchestrator|Retry belongs at the orchestrator, not only inside the request]]
- [[contexts/business/projects/data-platform/decisions/screening-idempotency-and-backfill|Key idempotency on the window, not the clock]]
- [[contexts/homelab/decisions/snaps-get-no-nvidia-opengl|A connected sandbox plug grants permission, not libraries]]
- [[contexts/business/projects/data-platform/decisions/stale-but-green|Stale-but-green: a cache serves confidently wrong numbers through every check meant to catch it]]
- [[contexts/homelab/decisions/storage-is-the-throughput-ceiling-not-the-network|Measure the storage before buying network — the spindle is usually the ceiling]]
- [[contexts/school/decisions/structure-the-data-dont-improve-the-heuristic|When extraction is wrong one time in four, author the data instead of improving the heuristic]]
- [[contexts/tooling/decisions/sync-logs-record-intent-not-writes|A sync log records intent, not writes]]
- [[contexts/tooling/decisions/sync-owns-obsidian-config-git-owns-content|Two writers with opposite conflict models on one file: the loser is whichever you checked last]]
- [[contexts/school/decisions/tbsrv-suite-fd-limit-not-inotify|The error message names what failed, not which limit was exhausted]]
- [[contexts/school/decisions/the-flake-was-a-config-value|A recurring flake diagnosed as a race was one number in a config file]]
- [[contexts/school/decisions/the-in-app-backup-task-still-writes-zero-bytes|A directory of correctly-named backups is the shape of a working backup, not evidence of one]]
- [[contexts/school/decisions/the-overdue-trigger-required-two-tables-to-agree|A predicate that requires two independently maintained tables to agree sees almost nothing]]
- [[contexts/school/decisions/thesis-app-dev-prod-split|A dev environment's isolations are fail-closed guards, not configuration]]
- [[contexts/tooling/decisions/thesis-app-is-the-primary-surface|A decision that divides work between two systems becomes a veto when one falls out of use]]
- [[contexts/school/decisions/todos-priority-meant-three-things|One column meaning three things at once, and the sort order that hid it]]
- [[contexts/business/projects/ontology-engine/decisions/transaction-time-is-writer-supplied|Transaction time is supplied by the writer, never defaulted by the database]]
- [[contexts/business/projects/ontology-engine/decisions/trl-2-is-the-claim|Software readiness is gated by integration and documented evidence, not by writing the code]]
- [[contexts/school/decisions/two-uis-two-namespaces-one-href|A link into the previous interface looks exactly like a working link]]
- [[contexts/business/projects/data-platform/decisions/window-not-offset-pagination|Backfill by disjoint windows, not offsets — and prove the filter was honoured]]
- [[contexts/homelab/decisions/xdg-desktop-must-be-a-real-directory|A missing XDG directory collapses to $HOME, and then tidying the desktop deletes your work]]

## Recently added (0)

Nothing yet.

## Gaps detected

None detected.

*Generated 2026-09-03 by `.brain/wiki-build.py`. Everything above the marker is hand-written; everything below it is not. A stale readout says so on its face.*
