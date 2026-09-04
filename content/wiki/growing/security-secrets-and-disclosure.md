---
type: hub
tier: growing
state: budding
publish: true
created: 2026-09-03
---

# Security, Secrets and Disclosure

*growing*

## What this hub is

Engineering records, all promoted out of `contexts/**/decisions/`, about
where a secret or a protected fact actually leaves a machine — not theory
about security, but a running log of specific leaks and specific fixes from
this vault's own tooling, from the workstation itself, from thesis-app, and
from the archived ontology-engine. Some of the projects behind them stopped;
nothing here says the reasoning did.

**The repeated correction is that the mitigation gets aimed at the wrong
layer first.** A password vault
([[contexts/tooling/decisions/bitwarden-fixes-rotation-not-leaking|bitwarden-fixes-rotation-not-leaking]])
solves the toil of finding every copy of a secret across files — but both
real leaks that prompted it were *output* events (a command printing a file,
an API echoing a key back), so a vault would have handed the identical value
to the identical transcript. The actual fix,
[[contexts/tooling/decisions/credential-guard-hook|credential-guard-hook]],
sits between a command and its output at the harness level, and even that
guard — built explicitly to stop leaks "not by remembering" — was walked
around five times over a month by ordinary diagnostics (`docker inspect`,
`~/.bash_history`, `pgrep -af`, `docker exec … env`) that the record had
already named in writing as gaps before each one happened. Naming a gap in a
document does not close it.

A second thread separates *disclosure* from *leaking*: what a system should
be allowed to send somewhere at all, as opposed to what accidentally escapes.
[[contexts/tooling/decisions/brain-reader-gates-disclosure-per-context|brain-reader-gates-disclosure-per-context]]
gates third-party inference per project context with two fail-closed
defaults — an unlisted context is local-only, a model of unknown location is
treated as remote — because a redactor can catch a leaked *value* but nothing
downstream can catch a policy violation carried in ordinary prose.
[[contexts/school/decisions/filling-a-column-changed-what-can-leave-the-box|filling-a-column-changed-what-can-leave-the-box]],
from the archived thesis-app, sharpens this: populating a database column
with text already sitting on disk quietly made that text reachable by a cloud
model, and nothing in the change said so. The general form it states is
blunt — a retrieval change is a disclosure change.

The third thread is that an enforcement boundary has to be structural, never
a convention obeyed by well-behaved code. thesis-app ingests the brain by an
explicit **allowlist**
([[contexts/school/decisions/thesis-app-reads-the-brain|thesis-app-reads-the-brain]])
rather than a directory walk, because a walk would have loaded the
redactor's own denylist — which holds real secret values by design — straight
into a search index. The ontology-engine's append-only assertion log needs
**two Postgres roles**
([[contexts/business/projects/ontology-engine/decisions/two-role-postgres-enforcement|two-role-postgres-enforcement]]),
because a single role that still owns its own schema can drop the trigger
that was supposed to make history immutable. And a flag that reads as a
security control,
[[contexts/tooling/decisions/allowed-tools-empty-does-not-disable-tools|allowed-tools-empty-does-not-disable-tools]],
turned out to do nothing when actually run — the same lesson from the
opposite direction: an unverified control is not a control.

Two further records fit no thread above: what
licensing risk in a regulated delivery actually reduces to
([[contexts/business/projects/ontology-engine/decisions/the-licence-worry-is-really-an-ato-worry|the-licence-worry-is-really-an-ato-worry]]) —
an SBOM and ATO argument, not a legal one — and why redaction has to key on
context rather than character class
([[contexts/tooling/decisions/redaction-is-proximity-scoped|redaction-is-proximity-scoped]]),
because a low-entropy password sitting next to the word "admin" leaked twice
before that rule was adopted.

<!-- GENERATED — everything below is rewritten nightly, do not edit -->
## Notes (0)

Nothing in the corpus matches this cluster yet.

## Engineering lessons (11)

- [[contexts/projects/thesis-app/decisions/a-downgraded-permit-must-drop-the-choice-it-authorised|A guard that revokes a permission must also revoke what was chosen under it]]
- [[contexts/tooling/decisions/allowed-tools-empty-does-not-disable-tools|An empty allowlist is not a denylist, and a headless agent call is not a model call]]
- [[contexts/tooling/decisions/bitwarden-fixes-rotation-not-leaking|A password vault fixes rotation toil, not leaking — they are different problems]]
- [[contexts/tooling/decisions/brain-reader-gates-disclosure-per-context|Gate disclosure per context with two fail-closed defaults: unlisted means local, unknown means remote]]
- [[contexts/tooling/decisions/credential-guard-hook|Stop credential leaks at the harness, not by remembering — and know the guard covers file reads, not process introspection]]
- [[contexts/school/decisions/filling-a-column-changed-what-can-leave-the-box|A retrieval change is a disclosure change]]
- [[contexts/tooling/decisions/redaction-is-proximity-scoped|Redaction keys on context, not on character class — and a secret-finding tool is itself a leak vector]]
- [[contexts/homelab/decisions/smb-share-runs-as-trevorb|Sharing as a sudo-capable account puts a root-equivalent password on the LAN]]
- [[contexts/business/projects/ontology-engine/decisions/the-licence-worry-is-really-an-ato-worry|Open-source licence risk in a regulated delivery is really an SBOM and ATO argument]]
- [[contexts/school/decisions/thesis-app-reads-the-brain|Ingest by allowlist, never by walk — and a supersession pointer must be followed when its target is itself superseded]]
- [[contexts/business/projects/ontology-engine/decisions/two-role-postgres-enforcement|Append-only needs two database roles, or the REVOKE is theatre]]

## Recently added (0)

Nothing yet.

## Gaps detected

None detected.

*Generated 2026-09-03 by `.brain/wiki-build.py`. Everything above the marker is hand-written; everything below it is not. A stale readout says so on its face.*
