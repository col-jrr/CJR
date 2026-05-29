---
name: ig-carousel
description: Generate a complete Instagram carousel from a topic. Trigger on phrases like "make me a carousel", "carousel about X", "IG post on Y". Outputs cover image, slide content, caption, and hashtags. Uses brand voice from CLAUDE.md.
---
# IG Carousel Generator
You generate complete, ready-to-post Instagram carousels in the user's brand voice.

## Inputs
- A topic (required)
- Slide count (optional, default 7-10)
- Audience override (optional, otherwise pull from CLAUDE.md)

## Process

### Step 1 — Research
Use web_search to find 3-5 credible, recent sources on the topic. Prioritize: official docs, peer-reviewed pieces, primary reporting. Skip listicles and SEO content. Take notes on the 3-5 strongest insights.

### Step 2 — Outline
Build a slide arc using this template:
- Slide 1: Hook (bold claim or surprising stat)
- Slide 2: Definition / context (dead simple)
- Slides 3 to N-1: One idea per slide. Show, don't tell.
- Slide N: CTA (comment a keyword, save, follow)

### Step 3 — Write
Each slide:
- Max 40 words
- Use the user's voice from CLAUDE.md
- One idea per slide. No mixing.
- Bold the hook word/phrase per slide

### Step 4 — Visuals
Generate the cover image using the user's brand style from CLAUDE.md. Other slides can be text-only or use generated visuals based on the topic. Always 4:5 aspect ratio (1080x1350).

### Step 5 — Caption
Write a caption with:
- A hook line (first 125 chars must work as preview)
- 3-5 lines of context that don't repeat the carousel
- A clear CTA matching the final slide
- A line break, then the hashtags

### Step 6 — Hashtags
Pick 15 hashtags ranked by fit, not size. Mix:
- 3-5 niche-specific (under 100k posts)
- 5-7 mid-tier (100k-1M)
- 3-5 broad (1M+)

## Output format
Return as: outline → slide-by-slide copy → caption → hashtags. Then ask "Approve and generate visuals?"

## Brand voice
Always check CLAUDE.md before writing. If it doesn't exist, ask the user to run the context-builder skill first.
