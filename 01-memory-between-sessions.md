# 1. Memory between sessions

## Problem
Every new Claude Code session starts empty. You re-explain who the client is, what you decided last Tuesday and why the previous attempt failed. In a team of three people and five sessions that re-explanation eats more time than the work.

## Setup (one hour, once)
1. Create a folder `vault/` next to your project. Inside: `people/`, `decisions/`, `insights/`, and a file `MEMORY.md`.
2. In `CLAUDE.md` add one paragraph: "Before building anything or answering a question about past work, read `MEMORY.md`, then search `vault/` for the topic. Build only after confirming we do not already have it."
3. `MEMORY.md` is an index, not a diary: one line per fact, under 150 characters, pointing to the note that holds the detail. Keep it under 200 lines; Claude loads it every session.

## The recipe (every session)
- **Start.** Claude reads `MEMORY.md`, searches `vault/` for the topic, and says in one line what already exists. We call this RECALL. It happens before the first edit, not after the first mistake.
- **During.** Any decision gets a note in `decisions/` with the date, the options considered and the one chosen. Any person gets a card in `people/` with how you met, what they need, what you promised.
- **End.** Claude appends one line per new durable fact to `MEMORY.md` and links the full note.

## The one rule
A memory record is never rewritten or deleted. When it turns out wrong, add `status: superseded`, `superseded_by: <new note>` and the date. The next session sees both the old belief and why it changed. Silent rewrites destroy trust in the whole folder.

## What broke for us
- The index grew past 200 lines and the tail silently stopped loading. Now a nightly script warns at 150.
- Two sessions edited the same note within minutes and one overwrote the other. Now every write logs who touched the file; a second author within 15 minutes triggers a conflict check.
- Claude built a transcription tool we already had. The RECALL step above is the direct result.

## Minimum viable version
A single `MEMORY.md` and the sentence in `CLAUDE.md`. Add folders when the file passes 50 lines.
