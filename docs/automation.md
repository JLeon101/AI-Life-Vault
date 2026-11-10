[ai-life-vault-automation-docs-automation-md.md](https://github.com/user-attachments/files/34613879/ai-life-vault-automation-docs-automation-md.md)
# Automation

## The two agents

Both agents are Markdown prompt files in `Agents/`, executed by a free CLI runtime. The runtime picks up its conventions from `AGENTS.md` in the vault root (with `GEMINI.md` and `QWEN.md` as drop-in copies for other runtimes). No paid service is involved anywhere in the loop.

### Source Processing Agent

Turns raw input into linked knowledge, one source at a time:

1. Read the material from the Inbox.
2. Create a lean source note: a thesis plus three to eight receipts, each quote tagged with a block ID.
3. Create or update atomic topic notes, every claim citing `[[Source_Note#^block-id]]`; prefer updating an existing topic over creating a duplicate (search first).
4. Attach front matter, at least two outbound links, and the Core Node footer in the same pass. No placeholder shells.
5. Log the run.

### Vault Audit Agent

Runs weekly as a health check and flags instead of fixing, the same discipline as a monitoring script that reports rather than auto-remediates:

| Check | What it catches |
|---|---|
| Orphans | Notes with fewer than two outbound links |
| Missing footers | Notes without the Core Node footer |
| Uncited claims | Topic bullets without a `[[...#^block-id]]` citation, flagged `[?]` plus a TODO |
| Hub property sync | Topic `hub` values that do not match an existing hub note |
| Temporal layer | Missing `created`, or event notes without date fields |
| Staging drift | Staging folders older than seven days sitting unapplied |

## Guardrails

* **Human territory is fenced.** Agents never edit `Projects/` or `Resources/Arguments/`. Planning and synthesis stay human. Agents process and audit; the human decides.
* **The log is mandatory.** Every run that creates, edits, archives, links, or deletes anything appends to the audit log. No-change runs log too. If an agent cannot write to the log, it must say so in its report instead of failing silently.
* **Remote changes are staged, never direct.** The in-chat AI drafts into staging; a human grants or denies by deletion; the local agent applies per the manifest (see Architecture).

## The audit log

The audit log is append-only. Each run gets a heading and one line per change:

```
- ACTION path — reason
```

plus a SUMMARY line per run. It is never rewritten, reordered, or trimmed. Combined with git's automatic commits, that yields two recoverable histories: intent (log) and state (git).

## Cost and failure modes

Runtime cost is $0: free CLI tier, free editor, free private repo, free sync. The failure modes are deliberate:

* **Runtime goes away?** The vault is plain Markdown; any other CLI agent that reads a conventions file can take over. The prompts are portable files.
* **Agent misbehaves?** It is only trusted to touch Resources and the Inbox; everything else requires a human.
* **Bad change lands?** Git rolls it back byte-for-byte, and the log explains what and why.
