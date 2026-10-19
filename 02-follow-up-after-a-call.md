# 2. Follow-up after a call

## Problem
The call goes well, both sides say "let's follow up", and nobody does. A follow-up written the same day converts; one written on Friday for Monday's call is an apology.

## Setup (thirty minutes)
1. A recorder that produces a transcript: a notetaker app, a recording pen, or the meeting tool's own transcript. Export to a folder `calls/` as text.
2. A folder `people/` with a card per contact (see workflow 1). If the card does not exist yet, this workflow creates it.
3. A short style note `voice.md`: five real messages the owner wrote, so Claude writes like the owner and not like a protocol bot.

## The recipe
1. Paste the transcript into the chat, or drop it into `calls/` once that habit exists. Ask Claude: "Follow-up for today's call with <name>."
2. Claude reads the transcript and the person's card, then produces three things:
   - **Follow-up message** in the owner's voice, under 80 words, one concrete next step with a date.
   - **Action items**, each with an owner and a deadline, taken only from what was actually said.
   - **Card update:** what was learned about the person, what was promised, what they need. Unknowns are marked "unconfirmed", never guessed.
3. The owner reads the message, edits if needed, and sends it from their own account. Claude does not send.
4. Every promise made on the call becomes a line in `promises.md` with a due date. A weekly check reads that file and lists what is overdue.

## The one rule
Claude drafts; the human sends. The follow-up goes through the channel where the person last replied, not the channel that is most convenient for you.

## What broke for us
- The first drafts were polite and empty. The `voice.md` file with real messages fixed this in one step.
- Claude invented an attendee who was mentioned but not present. Now the recipe says "only from what was actually said" and names the source line.
- Follow-ups were written and never sent because they sat in a file. Now the draft is shown in chat ready to paste, and the promise log nags.

## Minimum viable version
Paste the transcript into the chat and ask for a follow-up under 80 words in your voice. Add the files when you have done this three times.
