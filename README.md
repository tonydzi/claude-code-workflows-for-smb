# Claude Code workflows for SMB teams

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
