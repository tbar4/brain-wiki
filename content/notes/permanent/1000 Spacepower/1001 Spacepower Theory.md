---
stage: permanent
date: 2025-03-01
aliases:
  - Spacepower Theory
alias: Spacepower Theory
tags:
  - space-power-theory
LiteratureNote: "[[001 Zettelkasten/01 Literature/00 Books/The Origins of Victory|The Origins of Victory]]"
distilled: false
publish: true
---

previous note: [[1000 Spacepower]]
related note(s):
* 
# Spacepower Theory

Theory should be a way to assist in the education of the domain that is being studied for explanation purposes. For, spacepower theory,. the focus should be to explain the military-political relationships. Spacepower Theory is so new and technology is expanding and changing so rapidly that the aim of spacepower theory should be to create a firm list of questions that will inform the development and application of spacepower with the understanding that things can change rapidly. 


The definition of spacepower draws broadly from the definitions of power from other environments. It can be defined as "the ability in peace, crisis, and war to exert prompt and sustained influence in or from space". Spacepower is a child of the tension between America and the Soviets during the Cold War[3]. It can be simplistically stated as the ability to do something in space. Joshua Carlson's definition is a little more strict and is defined as "military force that can exert influence in and from the domain and create effects in other domains for strategic benefit". Once spacepower is projected out of orbit and into the "[[1001.1 "Silent Sea"|Silent Sea]]", spacepower operates more like traditional seapower[2].  Spacepower theory needs to provide a common framework which is universal and all can exploit to achieve policy objectives.

```base
properties:
  file.name:
    displayName: Linked Notes
views:
  - type: table
    name: People - Cards
    filters:
      and:
        - file.folder.startsWith("001 Zettelkasten/")
        - list(previousNote).contains(this)
    order:
      - file.name
    sort:
      - property: file.name
        direction: ASC

```

```dataview
TABLE WITHOUT ID 
	  link(file.name) as "Name"
	, link(alias) as "Alias"
WHERE 
	contains(file.path, this.file.folder) 
	AND file.name != this.file.name 
	AND file.name != "Attachments"
SORT Folder ASC
```


---
## References
1. [[Toward a Theory of Spacepower]] p.32
2. [[Spacepower Ascendant]]
3. [[Toward a Theory of Spacepower]]