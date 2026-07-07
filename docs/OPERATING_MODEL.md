---
id: pub-20260707-operating-model
created: 2026-07-07
type: operating-model
status: experimental
---

# PUNNARAJ Operating Model

This document records the current working model discussed during the 2026-07-07 design session.

It is not final infrastructure. It is a clean public reference so the design does not remain trapped inside a chat transcript.

## 1. Use existing provider ledgers, do not rebuild them

If a provider already keeps a reliable ledger, PUNNARAJ should reference it instead of duplicating it.

GitHub already keeps:

- commits
- branches
- diffs
- pull requests
- issues
- reviews
- comments
- workflow runs
- timestamps
- authorship

PUNNARAJ should not rebuild a GitHub clone. PUNNARAJ should add the missing layer:

- role
- meaning
- relation
- sensitivity
- cost
- risk
- recovery path
- rebuild priority

## 2. Build provider-exit capability, not duplicate infrastructure

GitHub can be the working ledger while it is useful.

ZERO or another controlled archive should hold enough mirrored data and metadata to rebuild elsewhere if GitHub disappears, locks access, or stops being useful.

The goal is not to avoid providers. The goal is to avoid dependency collapse.

## 3. Use connectors as inspection tools, not the core architecture

Connectors are useful for direct inspection:

- read Gmail
- inspect GitHub
- search Drive
- check Box archive

But connector-by-connector use is not a full operating system.

The long-term pattern is:

```text
Provider API / connector
→ adapter / worker
→ normalized event
→ event store / graph
→ MCP interface
→ AI / human review
```

## 4. Use MCP as a standard tool boundary

MCP should be used as a standard interface for tools, resources, prompts, and controlled operations.

MCP Inspector can serve as the development commander while the system is still being shaped.

PUNNARAJ should not design custom protocol layers until the standard layer proves insufficient.

## 5. Keep Obsidian vaults file-first

Obsidian vaults are useful because they are inspectable plain files.

An MCP vault server can help:

- scan notes
- detect missing `id`
- detect missing `created`
- suggest metadata
- suggest links
- create relation notes
- identify duplicates
- prepare patches for human review

AI should help organize the vault, not own the truth inside it.

## 6. Treat email as raw event evidence

A dump mailbox is not a human working surface. It is a raw event intake.

The system should:

- label provider events
- group duplicate candidates
- detect expected mail absence
- preserve access/security/billing evidence
- create deletion candidates only after classification

Deletion is allowed when evidence value, retention need, and human approval have been reviewed.

Keeping everything forever is not automatically safer. Unsearchable accumulation has cost.

## 7. Distinguish duplicate topology from abuse

Duplicate email or repeated records may be caused by forwarding chains, aliases, recovery paths, and multi-recipient provider alerts.

Duplicates should first become grouped evidence, not accusations.

The correct flow is:

```text
raw duplicate
→ duplicate candidate
→ canonical copy
→ relation to duplicate copies
→ retention decision
```

## 8. Protect human attention

Machine-manageable complexity should be handled by machines before humans are interrupted.

Humans should mainly be asked for:

- meaning
- authority
- high-risk decisions
- irreversible actions
- exception review

Normal routine should be summarized, not dumped into human attention.

## 9. Routine executive summaries

A useful PUNNARAJ routine report should cover:

- account and identity events
- access and security changes
- billing and cost risk
- provider state changes
- repository and deployment activity
- archive and Drive/Box changes
- duplicate or absence anomalies
- human action required

Normal events should be logged. Abnormal events should be surfaced.

## 10. User-owned memory graph

Photos, emails, notes, files, accounts, domains, devices, and repositories can become historical nodes when they are linked with provenance and meaning.

The goal is not consumer albums or scattered dashboards.

The goal is an inspectable, exportable, correctable memory graph owned by the user and family, with AI helping structure what machines can structure and humans correcting what only humans can know.
