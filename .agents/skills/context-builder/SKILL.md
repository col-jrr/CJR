---
name: context-builder
description: Interview the user about their business, voice, goals, and clients, then generate a complete CLAUDE.md file that every other skill will reference. Trigger on "build my CLAUDE.md", "set up my context", or when no CLAUDE.md exists in the project.
---
# Context Builder
You are interviewing the user to build their CLAUDE.md — the master context file every other skill reads.

## Rules of the interview
- Ask ONE question at a time. Wait for the answer.
- Don't move on until you actually understand the answer. Reflect it back if vague.
- Keep tone warm and conversational. This isn't a form.
- After all 7 answers, generate the CLAUDE.md file. Don't skip questions.

## The 7 questions
1. **What do you actually do?** "In one sentence, what's your business and who do you serve?"
2. **Who is your audience?** "Describe your ideal client/reader/customer. What do they struggle with? What do they want?"
3. **What's your voice?** "How do you talk? Pick adjectives: formal, playful, blunt, warm, technical, poetic. And what words/phrases do you use a lot? What words do you NEVER use?"
4. **What are your offers?** "List your products, services, and prices. Include any retainers, packages, or one-off services."
5. **Who are your competitors and what makes you different?** "Name 2-3 people doing similar work. What do you do differently or better?"
6. **What are your current goals?** "Short-term (next 90 days) and long-term (next 12 months). Be specific."
7. **What tools do you use?** "List the apps and platforms you live in: writing, design, scheduling, payments, social, project mgmt."

## Generate the file
After question 7, write CLAUDE.md to the project root with these sections:
```
# About me
[1-2 paragraphs combining Q1, Q2, Q5]

# Voice and tone
[Bullet list from Q3 — adjectives, signature phrases, banned words]

# Offers and pricing
[Table or list from Q4]

# Goals
- Short-term (90 days): [from Q6]
- Long-term (12 months): [from Q6]

# Stack
[Categorized list from Q7]

# Default output rules
- Always check this file before writing in my voice
- Never use [banned words from Q3]
- When unsure, ask before guessing
```
Save as CLAUDE.md in the project root. Confirm to the user. Tell them: "From now on, every skill will reference this file. You can edit it any time."
