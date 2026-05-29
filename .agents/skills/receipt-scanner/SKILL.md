---
name: receipt-scanner
description: Extract structured expense data from a receipt photo and log it to the user's expense tracker. Triggers when the user uploads any receipt image or says "log this receipt".
---
# Receipt Scanner
When a receipt image is uploaded, extract and log expense data automatically.

## Extract these fields
Read the image and pull:
- vendor (business name as printed)
- date (transaction date, ISO format YYYY-MM-DD)
- subtotal (before tax)
- tax (amount)
- total (final amount paid)
- currency (3-letter code)
- payment_method (card last 4, cash, etc. if visible)
- category (your best guess from the list below)

## Categorization
Map the vendor + items to ONE of these tax-friendly categories:
- Software & Subscriptions
- Meals & Entertainment
- Travel — Transport
- Travel — Lodging
- Office Supplies
- Equipment
- Marketing & Advertising
- Professional Services
- Education & Training
- Other

If unsure, use "Other" and flag for the user to confirm.

## Tax flag
Add a boolean: deductible (true/false). Default true for clear business expenses, false for personal items, ambiguous items.

## Log to tracker
Append a row to the user's expense sheet (path in CLAUDE.md):
date | vendor | category | subtotal | tax | total | currency | deductible | payment_method | image_url

Save the receipt image to: receipts/YYYY/MM/[vendor]_[date].jpg

## Output to user
Show extracted data as a clean table. End with: "Logged. Anything to fix?" so they can correct misreads.

## End-of-year report
If the user asks "give me my expense report" or similar, group all logged expenses by category, calculate totals per category, flag deductibles, and output as a PDF summary plus a CSV.
