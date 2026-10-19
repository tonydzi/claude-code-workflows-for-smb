# 4. Session retro

## Problem
A long working session with Claude produces one good tool, two good rules and a lesson you will need next month. All of it sits in a transcript nobody will read again. By the third session you are re-learning your own lessons.

## Setup (twenty minutes)
1. A file `retro-template.md` with three headings: **Keep · Drop · Try**.
2. A place where durable things go: `vault/insights/` for lessons, `vault/decisions/` for decisions, a `skills/` folder for reusable instructions, `MEMORY.md` for the index (workflow 1).

## The recipe
At the end of any session that produced something, say "retro". Claude then:
1. Lists what was built, what was decided and what failed, with the file or command as evidence.
2. Sorts each item: **Keep** (it worked, it goes to its home), **Drop** (it did not work, write one line why so nobody repeats it), **Try** (promising, not proven, parked with a date to revisit).
3. Writes each Keep item to its home: a lesson becomes a note, a repeatable instruction becomes a skill file (a plain Markdown page in `skills/` that `CLAUDE.md` tells Claude to read when the trigger word appears; nothing to install), a decision becomes a decision note with the alternatives considered.
4. Adds one index line per new home to `MEMORY.md`.
5. Prints a short hand-over block: "what we did, where it stands, next step", so the next session, or the next person, starts there.

A second trigger: after a task has been pushed forward three times with "continue", the fourth command is a retro, whether or not the task is finished. A session that has been continued three times is about to drown its own content.

## The one rule
Nothing reusable stays in the transcript. If it mattered, it has a file. If it has no file, it did not happen.

## What broke for us
- Retros became long essays nobody read. Now the hand-over block is five lines and the rest is in the notes.
- Dropped ideas came back every month under new names. The one-line "why dropped" journal stopped that.
- Skills written during the retro had no consumer and rotted. Now a skill names who uses it, or it is not written.

## Minimum viable version
End the session with "retro: Keep, Drop, Try, five lines" and paste the result into one notes file. Split into homes when the file is too long to scan.
