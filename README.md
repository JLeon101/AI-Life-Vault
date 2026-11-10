[ai-life-vault-readme.md](https://github.com/user-attachments/files/34613776/ai-life-vault-readme.md)
# AI Life Vault: How a Self-Auditing Second Brain Works

> A technical walkthrough of a personal knowledge vault built on plain Markdown: PARA + hub organization, a two-agent automation pipeline, citation-backed claims, and a git-backed audit trail. Total runtime cost: $0.

This repository documents a "second brain" system: a knowledge base where raw input (video transcripts, articles, course notes) is converted into linked, verifiable knowledge by a defined pipeline. It is built like a production system, with a single source of truth, change control, scheduled health checks, and versioned backup. Every factual claim in the vault traces back to a verbatim quote in a source note, and every change is logged.

* **Introduction**: What the vault is, the design constraints, and the methods it was built from.
* **Architecture**: The stack, the data flow, and the two layers of truth (audit log vs git).
* **Organization**: PARA folders, the Source/Topic/Argument taxonomy, hubs, and Bases dashboards.
* **Automation**: The two AI agents, their guardrails, and the append-only audit log.
* **Reference**: Folder map, note types, front-matter schema, and the link/citation grammar.

## What's in the vault

* **1 plain-Markdown vault**: every note is a text file. No database, no lock-in, clean git diffs.
* **2 AI agents on a free runtime**: one processes sources, one audits the vault. Both run from a free CLI runtime, no paid subscriptions.
* **6 live Bases dashboards**: saved queries over note metadata (topic rollup, reading list, arguments board, certification objectives, timeline, card-style library).
* **3 hard governance rules**: born-linked notes, cited claims only, append-only audit log.
* **$0/month**: editor, cloud sync, private git remote, agent runtime, and plugins all run on free tiers.

## How to read this repo

Start with [Introduction](docs/introduction.md) for the what and why, then [Architecture](docs/architecture.md) and [Organization](docs/organization.md) for how it works. [Automation](docs/automation.md) covers how it runs day to day, and [Reference](docs/reference.md) holds the schemas and inventory. Each page stands alone, so jumping straight to a topic works too.

> **Note**: This repository explains the system. It is not a template or a how-to guide, and it contains none of the vault's actual content; the vault itself stays private and syncs separately.

## Documentation

### Get Started

* [Introduction](docs/introduction.md)

### Explanation

* [Architecture](docs/architecture.md)
* [Organization](docs/organization.md)
* [Automation](docs/automation.md)

### Reference

* [Reference](docs/reference.md)
