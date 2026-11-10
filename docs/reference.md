[ai-life-vault-reference-docs-reference-md.md](https://github.com/user-attachments/files/34613900/ai-life-vault-reference-docs-reference-md.md)
# Reference

## Folder map

| Path | Contents |
|---|---|
| `Inbox/Transcripts_to_Process/` | Raw sources awaiting processing |
| `Inbox/Agent_Staging/` | Two-phase staging for remote changes, with run manifests |
| `Resources/Processed_Transcripts/` | Source notes (provenance anchors) |
| `Resources/Concepts/` | Topic notes (atomic, cited) |
| `Resources/Technologies/` | Technology dossiers (topic subtype) |
| `Resources/Arguments/` | Human-only synthesis |
| `Resources/Hubs/` | Hub dashboards (embedded Bases) |
| `Resources/Library/` | Library items (card view, cover images) |
| `Projects/`, `Areas/` | Human-authored plans and responsibilities |
| `Agents/` | Agent prompts and the bridge protocol |
| `Bases/` | Saved-query dashboards |
| `Archives/` | Retired material |
| `AGENTS.md` | Agent conventions (`GEMINI.md` / `QWEN.md` are runtime copies) |
| `Vault_Audit_Log.md` | Append-only change log |
| `STYLE_GUIDE.md` | Visual and content conventions |
| `Home.md` | Dashboard embedding the main Bases |

## Note types

| `type` | What it is | Who may create it |
|---|---|---|
| `source` | Provenance anchor: thesis plus receipts with block IDs | Agent or human |
| `concept` (topic) | Atomic concept note, every claim cited | Agent or human |
| `technology` | Topic subtype for tools and certifications | Agent or human |
| `hub` | Thin cluster dashboard embedding Bases | Human (agent verifies consistency) |
| `argument` | Synthesis: positions and conclusions | Human only |
| `project`, `area` | Plans and responsibilities | Human only |

## Front-matter schema

| Key | Applies to | Purpose |
|---|---|---|
| `type` | all notes | Note kind; drives Bases filters and agent rules |
| `status` | most notes | Lifecycle (queued, in-progress, done) |
| `hub` | topics and hubs | Hub membership; the grouping Bases query |
| `source id` / `url` | sources | Provenance back to the original material |
| `created` | all notes | Temporal layer; feeds Vault_Timeline |
| `event_date` (or `date_start`/`date_end`) | event notes | Timeline dots and bars |
| `tags` | all notes | Fixed vocabulary plus domain tags |

## Link and citation grammar

| Construct | Example | Meaning |
|---|---|---|
| Wikilink | `[[SQL_Window_Functions]]` | Unidirectional note link; backlinks are built automatically |
| Cited receipt | `[[Source_Note#^r3]]` | Points at a specific verbatim quote (block ID) in a source note |
| Core Node footer | `> Core Node: [[Projects/<root>]]` | Root anchor on every note |
| Uncited flag | `[?]` | Audit agent mark for a claim awaiting a citation |

## Bases inventory

Topic_Rollup, Reading_List, Arguments_Board, Cert_Objectives, Vault_Timeline, Library: six saved-query dashboards over front matter (see Organization).

## Vault stats (as of the last audit run)

| Metric | Value |
|---|---|
| Files at last local audit | 58 |
| Notes carrying the standard tag vocabulary | 49 |
| Live Bases dashboards | 6 |
| Agent runs logged | every session, including no-change runs |
| Monthly operating cost | $0 |
