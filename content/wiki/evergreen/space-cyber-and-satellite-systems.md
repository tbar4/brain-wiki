---
type: hub
tier: evergreen
state: evergreen
tags: [cyber-security, cyber-system-design]
publish: true
created: 2026-09-02
updated: 2026-09-02
---

# Space Cyber and Satellite Systems

*Draft header — written from the corpus, awaiting Trevor's revision.*

*evergreen · 44 notes · satellite systems from branch 1000, network warfare from 0000*

## What this corpus argues

The satellite half turns on a claim about where everyone else is looking.
[[1011.2 Cyber Security Satellite Research]] holds that satellite security research
has concentrated on *"protocols, encryption, and credential management"* — the data
link — while the exposure sits in the systems architecture.
[[1010.1 NASA Open Source Software]] names the mechanism: cFS made satellites
plug-and-play, and the bus that moves mission data between applications will move
an attacker's. [[1011.2.3 Software Bus Network Vulnerabilities]] and its children
demonstrate exactly that against OpenSatKit, and
[[1011.2.2 Encryption as a Single Source of Failure]] closes it — encryption done
correctly is still one point of failure. [[1011.1 Cyber as an ASAT Vector]] gives
the reason to care: a non-kinetic kill is available to an actor with no arsenal.

The 0000 half is not about satellites; it is about networks, and it comes from
different books. [[0105.2 Cyber Maneuvers will replace physical maneuvers]] argues
manoeuvre itself is moving into cyberspace and orbit;
[[0105.3.3 DoD has poor technical networks (i.e. data networks)]] says the DoD's
own networks are built by platform companies and do not connect. That is a
procurement argument, and it never touches a spacecraft.

The halves meet at one claim, stated twice.
[[1012.1 USSF needs to prepare for Cyber Warfare]] has Saltzman calling space and
cyber *"inextricably linked"*; [[1011.7 The First Space-Cyber War]] names the
Russo-Ukraine war as the case and
[[1011.4 Russian cyberattack on US made ViaSat]] the incident. That is also the
boundary with Spacepower — a note belongs here when the thing under attack is a
system, a bus or a link or a ground station, rather than a domain — and
[[0105.3.2.1 The Chinese "Systems Destruction Warfare"]] sits honestly on it.

**Where the corpus disagrees:** it does not. Nothing asks whether a resilient
network and a hardened bus are the same fix. The two answers were never set
against each other.

**Gap:** the three notes that would say what any of this *is* —
[[1010 Satellite Software]], [[1011 Satellite Cyber Security]] and
[[1012 USSF Cyber Security]] — contain no prose whatsoever. The cluster's
most-cited source is also unreachable from it: eighteen permanent notes cite
`Securing the Final Frontier - United States Space Force Cybersecurity Capabilities`,
while the note on disk is
[[notes/literature/Securing The Final Frontier- United States Space Force Cybersecurity Capabilities|filed with its colon flattened to a hyphen]],
so all eighteen dangle. And a shelf of space-cyber reading sits uncited by any note
in the cluster, [[notes/literature/WannaFly- An Approach to Satellite Ransomware|WannaFly]] among
it. The reading has outrun the distilling.

<!-- GENERATED — everything below is rewritten nightly, do not edit -->
## Notes (49)

**1000 Spacepower** (27)

- [[1004.2 Space Hybrid Operations]]
- [[1010.2 Satellite Software Bus]]
- [[1011 Satellite Cyber Security]]
- [[1011.1 Cyber as an ASAT Vector]]
- [[1011.1.1 Most common types of sophisticated attacks]]
- [[1011.2.1 Leading Satellite Cyber Security Researchers]]
- [[1011.2.2 Encryption as a Single Source of Failure]]
- [[1011.2.3 Software Bus Network Vulnerabilities]]
- [[1011.2.3.1 Single Component Reliability in Software Bus]]
- [[1011.2.3.2 Lack of Software Bus Permissions and Encryption]]
- [[1011.2.3.3 Simulated Cyber Attack on Satellite Network]]
- [[1011.2.3.3.1 No-Op Vulnerability]]
- [[1011.2.3.3.2 DoS Attack]]
- [[1011.2.3.3.3 Exploit Command]]
- [[1011.2.3.3.4 Brute Force Command]]
- [[1011.3 Satellite Cyber Security Recommendations]]
- [[1011.3.1 Cyber Info Sharing Recommendations]]
- [[1011.3.2 Satellites present an outsized opportunity for hackers]]
- [[1011.3.3 Space Systems Orgs introduce risk by not distinguishing between Internal IT and Operational IT]]
- [[1011.4 Russian cyberattack on US made ViaSat]]
- [[1011.5 GPS Spoofing]]
- [[1011.6 Satellite Mfgs focus on Function over security]]
- [[1011.7 The First Space-Cyber War]]
- [[1012 USSF Cyber Security]]
- [[1012.1 USSF needs to prepare for Cyber Warfare]]
- [[1012.2 USSF Cyber Sec Training]]
- [[1012.3 USSF will need to contend with more Cyber attacks]]

**0000 Military Sciences** (22)

- [[0105 Cyber, Comms, Systems, Networks Warfare]]
- [[0105.1 Cyber Warfare]]
- [[0105.1-a Private Entity support of Military Space Operations]]
- [[0105.1.1 Chinese Cyber Attacks on American Military contractors]]
- [[0105.1.2 Stuxnet]]
- [[0105.1.3-a Microsoft support against Russian cyber attacks in Ukraine]]
- [[0105.1.4-a Difficulties of determining origin and prosecuting cybercrime]]
- [[0105.1.5-a cyber has a lot of opportunity for war gaming]]
- [[0105.2 Cyber Maneuvers will replace physical maneuvers]]
- [[0105.2.1 US Military's main priority should be more resilient networks]]
- [[0105.3 Battle Networks]]
- [[0105.3.1 Communications will transition from human to human into computer to computer]]
- [[0105.3.2-a Chinese Journal predicts future war will be fought in space and cyber]]
- [[0105.3.2.1 The Chinese "Systems Destruction Warfare"]]
- [[0105.3.3 DoD has poor technical networks (i.e. data networks)]]
- [[0106.3 Signals & Communications]]
- [[0106.3.2 Lasers & Advanced Communications]]
- [[0106.4-a Big Data will be the bottleneck in AI]]
- [[0106.4.1-a1 Big Data, AI, and how to win Scouting War]]
- [[0108.1-b1 DoD needs more of a software focus]]
- [[0109.3.1 Communications Network Modeling important for Net Assessment]]
- [[0110.3-a Many claiming most dramatic revolution warfare has begun]]

## Recently added

No usable recency signal. 49 of 49 notes in this hub share one file date (2026-09-03, a bulk frontmatter rewrite), and `created:` is absent from most of the corpus. Recency here would be an artefact of a tool run, not of when anything was written.

## Gaps detected

None detected.

*Generated 2026-09-03 by `.brain/wiki-build.py`. Everything above the marker is hand-written; everything below it is not. A stale readout says so on its face.*
