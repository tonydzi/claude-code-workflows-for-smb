# 3. Leads from your camera roll

## Problem
At a conference you take a photo with a person and a screenshot of their contact or chat so you do not forget. A week later there are 300 photos, 20 of them are leads, and none of them are in your CRM.

## Setup (two hours)
1. An export of new photos from the phone to a folder `inbox-photos/` (cloud photo sync, a weekly export, or a cable).
2. OCR on each image. Any free on-device OCR works; the point is that text extraction is a script, not a model call.
3. A `people/` folder from workflow 1 and a `promises.md` file from workflow 2.

## The recipe
1. A script runs weekly: exports new photos, runs OCR, writes one line per image to `manifest.jsonl` with the timestamp and the recognised text. Zero model calls so far.
2. Claude reads the manifest and classifies every image with one word:
   - `family`: stop immediately, nothing is written anywhere.
   - `screen`: a screenshot of a chat, a profile or a business card. Becomes a person card and, if there is a promise in the text, a line in `promises.md`.
   - `selfie-with-lead`: a photo with a person. Paired with the nearest `screen` by time (within ten minutes) to attach a name.
   - `conference`: a stage, a badge, a slide. Becomes context on the event, not a person.
   - `document`: a whiteboard, a contract page. Goes to a notes folder.
3. Each person card carries the full context of the meeting: date, event, where you met, why it matters, what they need, what was promised, what is still unconfirmed.
4. Claude reports: "N photos, M leads created, K promises logged, J skipped as personal."

## The one rule
Personal photos are never looked at twice. The `family` class is the first check and it ends processing. Lead work is not worth a leak of family life into a work folder.

## What broke for us
- A binary "lead or not lead" classifier lost agreements hidden in chat screenshots. The five classes replaced it.
- Running the export every two hours burned battery and nerves. Weekly, Monday morning, with a manual run right after a conference.
- Photos of other people's screens were attributed to the person in the selfie. The pairing is now by time window only, and anything outside it stays "unconfirmed".

## Minimum viable version
After the conference, drop the 20 photos into the chat and ask for a card per person with the five-class rule. Automate once you have done it twice.
