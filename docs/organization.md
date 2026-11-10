[ai-life-vault-organization-docs-organization-md.md](https://github.com/user-attachments/files/34613859/ai-life-vault-organization-docs-organization-md.md)
# Organization

## PARA: the folder skeleton

| Folder | Holds | Layman version |
|---|---|---|
| Projects/ | Active project plans, human-authored only | Things with a finish line |
| Areas/ | Ongoing responsibilities | Things that never finish but recur |
| Resources/ | The knowledge itself: Hubs, Concepts, Technologies, Processed_Transcripts (sources), Arguments, Library | The reference library |
| Archives/ | Retired material | Cold storage |
| Inbox/ | Raw captures and agent staging | The loading dock |

PARA (Projects, Areas, Resources, Archives) gives every file exactly one home based on its relationship to the owner: active, recurring, reference, or retired. Agents process Resources and Inbox; Projects and Areas are human territory.

## The STA taxonomy: three kinds of notes

The epistemic core is that knowledge has three distinct layers, and blurring them is how notes rot.

* **Source notes** are provenance anchors: one per input (a video, an article, a course module). They stay lean: a thesis in one or two sentences, then three to eight receipts, verbatim quotes each tagged with a block ID. They are the vault's evidence store.
* **Topic notes** are atomic: one concept per note (a technology, a technique, a term). Every factual claim inside cites its source with `[[Source_Note#^block-id]]`, so any claim can be traced to the exact quote it came from. Technologies are a subtype of topic with the same rules.
* **Argument notes** are the synthesis layer: positions, conclusions, and decisions built from topics. Only the human writes these, which keeps judgment where it belongs.

The effect is a citation chain: Argument → Topics → Sources → the original material. Nothing in the vault is "I read this somewhere"; it is "this claim, from this receipt, in this source".

## Hubs and Bases: navigation that maintains itself

Classic note systems use "maps of content" (MOCs): manually curated index notes. They rot, because curation is manual. This vault replaces them with two mechanisms:

* **Hubs** are thin dashboards, one per knowledge domain, that mostly embed Bases queries. Grouping is driven by the `hub` property in each note's front matter, so a note joins a hub by being tagged, not by someone remembering to add a link.
* **Bases** are saved queries over front matter, effectively SQL views for notes. Six are live:

| Base | Purpose |
|---|---|
| Topic_Rollup | All topic notes with status and hub grouping |
| Reading_List | Sources queued or in progress |
| Arguments_Board | Argument notes by status, kanban-style |
| Cert_Objectives | Certification study progress |
| Vault_Timeline | Every note and event on a timeline (dots for dates, bars for ranges) |
| Library | Card-style view of library items with cover images |

Because a dashboard is a saved query, it cannot drift from the data: it is always current because it is derived, not maintained.

## Note anatomy: the born-linked rule

Every note is born linked, which is what keeps the graph useful instead of a pile of orphans:

* **Front matter** on every note: `type`, `status`, `hub` (for topics and hubs), `created`, and `tags`; source notes also carry `source id` and `url`. This is the structured metadata the Bases query.
* **Two or more outbound links** to canonical nodes (topics, hubs, technologies, projects, sources) are required at creation.
* **A Core Node footer**: every note ends with a link back to a single root project note, tying the whole graph to one anchor.
* **A temporal layer**: `created` on everything; event notes add `event_date`, or `date_start`/`date_end` for ranges, which feeds the timeline Base.

Tags follow a fixed vocabulary (concept, technology, hub, source, project, area, dashboard, meta, audit, daily, plus domain-specific tags), so search and Bases filters behave predictably.

## Naming and style

Filenames use underscore/TitleCase (`SQL_Window_Functions.md`), acronyms uppercase (AI, LLM, SQL). A style guide defines the callout vocabulary and cover-image rules, and a CSS snippet layer keeps visual styling consistent. Content conventions matter more than looks, though: lean sources, atomic topics, cited claims.
