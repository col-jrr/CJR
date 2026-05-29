---
name: invoice-generator
description: Create and send a branded invoice PDF when the user says "invoice [client] for [project]". Pulls deal terms from notes, calculates total with tax, generates a branded PDF, emails it to the client, and logs it.
---
# Invoice Generator
When the user says "invoice [client name] for [project]", you handle the entire billing flow.

## Step 1 — Pull deal info
Search the user's notes/Notion/Drive for:
- Client legal name + billing email + billing address
- Project scope and agreed fee
- Payment terms (net 7, net 14, net 30)
- Any retainer/deposit already paid
- The user's tax setup (VAT, GST, none)

If anything is missing, ask before proceeding. Do not invent numbers.

## Step 2 — Calculate
- Subtotal = agreed project fee minus any deposit paid
- Tax = subtotal × user's tax rate (from CLAUDE.md)
- Total = subtotal + tax
- Due date = invoice date + payment terms

## Step 3 — Generate PDF
Use the pdf skill (reportlab) to build a branded invoice with:
- Header: User's business name + logo + handle
- Invoice number (format: INV-YYYY-NNN, auto-increment from last invoice)
- Issue date + due date
- "Bill to" block (client legal name + address)
- Line items table: description, qty, rate, amount
- Subtotal / Tax / Total rows
- Payment instructions block (bank details OR payment link from CLAUDE.md)
- Footer: thank you note + late payment terms

Brand colors and fonts come from CLAUDE.md. Save as: invoices/INV-YYYY-NNN_clientname.pdf

## Step 4 — Email
Use Gmail to send. Subject: "Invoice INV-YYYY-NNN from [User's business name]". Body: short, warm, includes total + due date + payment link. Attach the PDF.

## Step 5 — Log
Append a row to the user's income tracker (Sheet/Notion):
date | invoice # | client | amount | tax | total | status:sent | due date

## Confirmation
Before sending, show: total amount + recipient email + PDF preview. Get a yes. Don't send silently.
