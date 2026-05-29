---
name: client-onboarding
description: Run the user's full new-client onboarding flow. Trigger on "onboard [client name] for [service]" or "new client: [name]". Sets up project folder, sends welcome email, books kickoff call, adds to CRM, creates Slack channel.
---
# Client Onboarding
When a new client signs, run the full onboarding flow without follow-up questions where possible.

## Inputs needed
- Client name (full)
- Client email
- Service type (must match a service in CLAUDE.md offers)
- Project start date
- Anything else? Ask in one consolidated message if missing.

## Step 1 — Project folder
In the user's Drive, create:
clients/[client name]/[YYYY-MM service-type]/

Inside, copy the templates from: templates/[service-type]/
(Templates path is in CLAUDE.md. If no template exists for that service, create the empty folder and flag it.)

## Step 2 — Welcome email
Draft and send via Gmail.
Subject: "Welcome to [User's business] — let's get started, [first name]"
Body covers:
- Warm welcome (1-2 lines, in voice)
- What happens next (3-step bullet list)
- Kickoff call link (from Step 3)
- Reply-to address
- Sign off

## Step 3 — Kickoff call
Book a 30-min event on the user's calendar:
- Title: "Kickoff: [User's business] x [Client name]"
- Time: First available slot 2-5 business days after the project start date, in the user's working hours from CLAUDE.md
- Invite: client email + user
- Description: Agenda (Goals / Timeline / Deliverables / Communication cadence)
- Add Google Meet or Zoom link automatically

## Step 4 — CRM entry
Add to the user's CRM (location in CLAUDE.md):
- Name, email, company
- Status: Active
- Service: [type]
- Start date, expected end date
- Notes: link to project folder + kickoff event

## Step 5 — Slack channel (if Slack is in stack)
Create a private channel: client-[lastname-projecttype]
Invite the user. Pin the project folder link as the first message.

## Confirmation
After all steps, return a single recap:
- Folder: [link]
- Welcome email: sent to [email]
- Kickoff: [date/time] — [meet link]
- CRM: updated
- Slack: [channel name]

Ask: "Anything to adjust?"
