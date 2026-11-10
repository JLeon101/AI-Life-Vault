[ai-life-vault-introduction-docs-introduction-md.md](https://github.com/user-attachments/files/34613827/ai-life-vault-introduction-docs-introduction-md.md)
# Introduction

## What this is

A "second brain" is external memory: a place where raw material is captured now so it can be found, trusted, and reused later. This one is an Obsidian vault, which in practice is a folder of plain Markdown files with an editor and a link syntax on top. The editor is replaceable; the files are the actual system. If the app disappeared tomorrow, every note would still open in any text editor or IDE.

The interesting part is not the app, it is the operating model around the files:

* **Verifiable knowledge.** Every factual claim in a topic note cites the source note and block it came from. Uncited claims are flagged automatically.
* **Agent-assisted, human-governed.** Two AI agents handle the repetitive work: processing sources and auditing structure. Synthesis and planning are reserved for the human.
* **Change control.** An append-only audit log records every change with a reason, and git provides byte-level version history. Nothing mutates silently.
* **Zero cost.** Every component runs on a free tier, so the system has no recurring cost and no subscription dependency.

## Why those constraints

Plain Markdown is the same bet as keeping documentation in text files instead of a proprietary tool: it diffs cleanly, it outlives any vendor, and it lets git be the source of truth. The $0 constraint is deliberate as well. A system that depends on a paid runtime dies the day the card expires; this one has no such dependency, which also makes any piece of it safe to adopt elsewhere without a budget conversation.

## Where the design came from

The system is a deliberate hybrid of two public methods, compared dimension by dimension (organization paradigm, note anatomy, linking model, graph structure, automation role, maintenance cadence, tooling cost) before merging:

| Method | What it contributed |
|---|---|
| Zen van Riel's AI Knowledge Graph | PARA folder structure, hub-based graph, the born-linked rule, the two-agent pattern (process + audit) |
| Ilya Shabanov's Source/Topic/Argument (STA) system | The Source/Topic/Argument taxonomy, every-claim-cites-a-source, Bases dashboards instead of manually curated maps, human-only argument notes |

From the first method came the automation spine; from the second, the epistemics (how claims are provenanced) and the navigation model. Where they disagreed, the tie-breakers were mechanical: an append-only log for narrative, git for proof.

## The managed-services framing

For readers from a managed services background, the mapping is direct. The vault is a knowledge base with change management. The audit agent is a scheduled health check, the way an RMM script flags drift. The staging area for remote changes is a change window: drafts land there, a human approves or denies, and a local agent applies and logs. Git is configuration backup with history. Front matter on each note is structured metadata, like custom fields on a configuration item. The point of the system matches the point of any documented environment: once something is written down with provenance, it never has to be re-derived from memory.
