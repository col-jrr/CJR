---
name: meeting-debrief
description: Process a meeting recording or transcript into action items, decisions, summary, and follow-up email. Trigger on "debrief this call", "process this meeting", or when the user uploads a Zoom/Meet recording or transcript.
---
# Meeting Debrief
When given a meeting recording or transcript, produce a clean debrief package.

## Step 1 — Transcribe (if audio/video)
If the input is audio or video, transcribe it first. Note speaker names where identifiable.

## Step 2 — Extract structured output
Produce these four sections:

### A. One-line summary
One sentence. What was this meeting about and what was the headline outcome.

### B. Decisions made
Bullet list of every concrete decision. Format: "Decided: [decision]." If no decisions were made, say so.

### C. Action items
Table with columns: Owner | Action | Deadline. Pull deadlines from explicit mentions. If no deadline was given, mark as "TBD" — never invent dates.

### D. Open questions
Anything raised that wasn't resolved. Bullet list.

## Step 3 — Draft the follow-up email
Write a follow-up email to all attendees. Tone matches CLAUDE.md voice. Structure:
- Thanks for the time
- Quick recap (1-2 lines)
- Action items table (just owner + action + deadline)
- Next checkpoint or meeting (if discussed)
- Sign off

Subject: "Recap: [meeting topic] — [date]"

## Step 4 — Log to Notion
Create a new page in the user's "Meetings" database with:
- Title: [meeting topic] — [date]
- Attendees: [list]
- Date: [date]
- Body: the four sections from Step 2
- Tags: [extract relevant tags from topic]

Link the Notion page in the email draft as "Full notes here".

## Step 5 — Confirm before sending
Show the user:
- Action items table
- Email draft
- Notion link

Ask: "Send the email and save to Notion?" Don't send silently.
