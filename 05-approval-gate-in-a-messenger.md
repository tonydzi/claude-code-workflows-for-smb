# 5. Approval gate in a messenger

## Problem
Claude is running a task at night and hits a step that needs a human yes: spend money, send something outward, delete something. Nobody is at the terminal. The run either stops dead until morning or guesses and does it anyway. Both are bad.

## Setup (one hour)
1. A messenger channel the owner actually reads on the phone (a private group in whatever you already use).
2. A small script `ask.py` that posts a question to that channel and waits for a reply: `+` means yes, anything else means no, silence for N minutes means the default.
3. A one-page list of **decision classes** in `CLAUDE.md`. Ours:
   - **A** internal and reversible: decide yourself, report afterwards.
   - **B** our content into our own channels: decide yourself.
   - **C** short business message outward: decide yourself.
   - **D** needs human hands (a code from a phone, a physical click): ask.
   - **E** money, irreversible deletion, secrets to a third party, mass sending: ask and wait.

## The recipe
1. At the fork, Claude names the class in one line. A, B, C: proceed and log before and after.
2. D or E: post one line to the channel: what, why, what changes, what the default is if nobody answers. Keep working on everything that does not depend on the answer.
3. `+` comes back: proceed and log the approval with its timestamp. Anything else: stop that branch, finish the rest, report.
4. Silence: re-ping once after 30 minutes; after that, apply the stated default (for E the default is always "do not").
5. Cap: two asks per run. A run that needs a third ask is badly specified; it stops and reports instead.

## The one rule
An ask never stops the whole run, and a reversible step never waits for a human. Waiting is more expensive than a mistake you can undo. For irreversible steps the opposite holds: no reply means no.

## What broke for us
- Twenty copies of the same question arrived from twenty sessions. Now identical asks are collapsed into one line with a count.
- The owner answered "ok" in another chat and the run never saw it. Now the rule is one channel, one symbol.
- Claude asked for approval on things it could decide. The class list, written down, removed most of the questions.

## Minimum viable version
No script: Claude writes the question to a file `ASK.md` and stops that branch; the owner opens the file in the morning and types the answer. Add the messenger when the morning delay starts costing.
