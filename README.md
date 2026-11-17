# claude-code-workflows-for-smb

Five one-page recipes that show a small team how to use Claude Code every day: memory between sessions, call follow-ups, leads from photos, session retros and approvals by chat.

**Who it's for:** non-engineers and small business teams, and trainers who teach them.
**What you get:** five short workflows, each with setup steps, the one rule that makes it last, and a minimum version you can start in under an hour.

## Quick start
1. Open [01-memory-between-sessions.md](01-memory-between-sessions.md) and follow its "Setup" section (one folder, one index file, one sentence in CLAUDE.md).
2. Run one normal session and let Claude read the index first. Before you close it, ask Claude to add one line to `MEMORY.md` about something you decided (otherwise the next session has nothing to remember).
3. Pick the next workflow from the table below that matches your pain.

**Done when:** a new Claude Code session tells you in one line what you already decided or built before, without you explaining it again.

> Want an AI agent to do it for you? Paste this to Claude Code / Codex / Cursor:
> "Read the 'For AI agents' section of https://github.com/tonydzi/claude-code-workflows-for-smb and set it up for me."

## For AI agents

### Preconditions
- Claude Code or any agent that reads CLAUDE.md or AGENTS.md. No package manager, runtime or account is needed. The repo is Markdown only.
- Ask the human: which workflow (1 to 5) they want, and where their project folder is.

### Use
1. `git clone https://github.com/tonydzi/claude-code-workflows-for-smb` and read the chosen page (`01-memory-between-sessions.md` to `05-approval-gate-in-a-messenger.md`).
2. Do the page's "Setup" and "Minimum viable version" only. Workflow 1 comes first; the other four assume a folder of Markdown notes exists.
3. For workflow 1 concretely: create `vault/` with `people/`, `decisions/`, `insights/` and a `MEMORY.md` index, then add the RECALL paragraph from the page to the project's CLAUDE.md.

### Configure
Only the project folder path and the paragraph added to CLAUDE.md. Workflows 3 and 5 involve photos and a messenger: ask the human before touching either, and never send anything on their behalf.

### Verify
1. Make sure `MEMORY.md` has at least one real line about a topic (write one with the human if the setup session did not: for example `- 2026-01-05 chose weekly invoicing, see decisions/invoicing.md`, plus that note).
2. Check the paragraph landed: the project's `CLAUDE.md` contains the RECALL sentence, and the file was appended to, not overwritten.
3. Start a fresh session in the project and ask "what do we already have about <that topic>?". Expected: the agent reads `MEMORY.md` first and answers in one line from that note, naming it. If it answers generically or says it knows nothing, the setup failed (wrong folder, or `CLAUDE.md` not in the project root). With an empty `MEMORY.md` this test proves nothing, so do step 1 first.

### Uninstall / rollback
Delete the `vault/` folder you created (only if this setup created it and the human agrees) and remove the added paragraph from CLAUDE.md.

### Rules for the agent
- Never delete notes. Mark them `status: superseded` and link the new one.
- Draft messages, do not send them. The human presses send.
- No secrets in notes or in CLAUDE.md.

## Details

Five one-page workflows we run every day in a small operating team: one human operator and a few Claude Code sessions. Each page is a recipe a non-engineer can follow in an afternoon, with the rule that made it survive contact with real work.

Written for Approved Claude SMB Trainer cohorts to reuse in workshops. Take them, rename them, teach them. MIT.

| # | Workflow | Pain it removes | Time to first result |
|---|---|---|---|
| 1 | [Memory between sessions](01-memory-between-sessions.md) | Every new chat starts from zero | 1 hour |
| 2 | [Follow-up after a call](02-follow-up-after-a-call.md) | Call ends, follow-up never gets written | 30 minutes |
| 3 | [Leads from your camera roll](03-leads-from-the-camera-roll.md) | Conference photos and contact screenshots die in Photos | 2 hours |
| 4 | [Session retro](04-session-retro.md) | Good tricks drown in long transcripts | 20 minutes |
| 5 | [Approval gate in a messenger](05-approval-gate-in-a-messenger.md) | Agent needs a yes, nobody is at the keyboard | 1 hour |

## How to teach them

Each page has the same shape: **Problem · Setup · The recipe · The one rule · What broke for us · Minimum viable version**. Run workflow 1 first; the other four assume Claude can read and write a folder of Markdown notes. Workflow 4 is the one that keeps the other three alive.

A 4-hour workshop maps onto them like this: hour 1 = workflow 1 (structure and memory), hour 2 = workflow 2 (first artifact), hour 3 = workflow 4 as the first skill the group writes, hour 4 = pick 3 or 5 depending on the room. For a room that "just chats", teach 3 and 5 from their **Minimum viable version** only: upload photos straight into Claude, write the question to a file. The scripts are the second workshop, not the first.

## Ground rules we learned the hard way

1. Markdown files in a folder beat any database you have to maintain. Claude reads them natively, humans can fix them with a text editor.
2. The cheapest tool goes first: a script counts, filters and dedupes; the model judges and writes.
3. "Done" is a claim. The report carries the command and its output, not the word "checked".
4. Nothing goes out on the owner's behalf without the owner pressing send. Claude drafts, the human sends.
5. Never delete. Supersede: mark old notes as superseded and link the new one.

## Where this comes from

A one-operator lab that has run a fleet of Claude Code sessions across several machines since June 2026. Everything here is sanitized from a live system: real failures, no internal names.

---
Anton Dziatkovskii · github.com/tonydzi

## AI contributors

This project is built by a human + AI team. Credit for AI tools on commits follows one policy, one source for every repo: [AI-CONTRIBUTORS.md](https://github.com/tonydzi/.github/blob/main/AI-CONTRIBUTORS.md).
