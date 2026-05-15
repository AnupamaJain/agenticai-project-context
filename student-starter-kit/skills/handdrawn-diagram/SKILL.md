---
name: handdrawn-diagram
description: Generate hand-drawn whiteboard infographic prompts for any project, product, or concept. Produces Gemini-ready prompts that create branded notebook-style diagrams with flash cards, logos, architecture, and AiwithDhruv branding. Use when user asks for a diagram, infographic, visual explainer, project overview image, or README visual.
argument-hint: "[topic]"
---

# Hand-Drawn Whiteboard Diagram Generator

## Goal
Generate copy-paste-ready prompts for Google Gemini image generation that produce hand-drawn whiteboard/notebook style infographic diagrams. These diagrams explain a project, product, or concept visually — perfect for GitHub READMEs, LinkedIn posts, Instagram, YouTube thumbnails, and documentation.

## When to Use
- User asks for a "diagram" or "visual explainer" for a project
- User needs a README hero image
- User wants to explain architecture/flow visually
- User wants social media infographic
- User says "like the portfolio diagram" or "hand-drawn notes"

## The Proven Formula

Every diagram follows this exact zone layout that was validated on the AiwithDhruv Portfolio project:

```
+------------------------------------------------------------------+
|  TITLE + SUBTITLE                          | BRAND BADGE          |
+------------------------------------------------------------------+
|                    |                        |                      |
|  LEFT COLUMN       |  CENTER COLUMN         |  RIGHT COLUMN        |
|  (Prerequisites/   |  (Main Flow/Process)   |  (Result/Output)     |
|   What You Need)   |                        |                      |
|                    |  FLASH CARDS scattered  |  Browser/App mockup  |
|  Checklist with    |  around as sticky notes |  with content inside |
|  logos next to     |                        |                      |
|  each item         |  Flowchart with boxes   |                      |
|                    |  connected by arrows    |                      |
+------------------------------------------------------------------+
|  ARCHITECTURE DIAGRAM    |  STATS ROW        |  BRANDING + AUTHOR  |
|  (boxes with logos,      |  (circled numbers  |  (name, socials,    |
|   connected by arrows)   |   with highlights) |   portrait sketch)  |
+------------------------------------------------------------------+
```

## Style Constants (NEVER change these)

```
PAPER:       White lined notebook paper, subtle horizontal lines
SURFACE:     Sits on natural wooden desk, visible at edges
MARKERS:     Black marker for text/lines, cyan (#00D4FF) for highlights
HIGHLIGHTS:  Yellow highlighter for key numbers and stats
FLASH CARDS: Pastel colored sticky notes (yellow, blue, pink, green, purple)
             Tilted at slight angles, some with paper clips or tape
LOGOS:       Small hand-drawn recognizable logos next to every tech/tool name
TEXT:        Hand-written, slightly imperfect but always readable
AMBIENT:     Coffee ring stain (subtle), blue pen on desk, star doodles
BRANDING:    "AiwithDhruv" in 3+ spots (badge, watermark, bottom-right)
RATIO:       16:9 landscape (for GitHub/YouTube) or 4:5 (for LinkedIn/Instagram)
VIBE:        Photo of a real whiteboard after a brainstorming session
```

## Anti-Patterns (NEVER do these)
- NEVER use computer/digital fonts — everything hand-drawn
- NEVER make it look like a Canva template or polished design
- NEVER leave the browser mockup blank — always fill with content
- NEVER forget logos next to tech names
- NEVER skip the flash cards — they add color and scannability
- NEVER skip branding — minimum 3 spots
- NEVER make it too clean — slight messiness = authenticity
- NEVER use the word "infographic" in the prompt to Gemini (triggers digital look)

## Prompt Template

Replace everything in [BRACKETS] with project-specific content:

```
Hand-drawn whiteboard infographic on white lined notebook paper, sitting on a natural wooden desk surface visible at the edges. Black marker lines, cyan (#00D4FF) marker highlights, yellow highlighter on key numbers. Real marker ink texture, natural paper grain. Photo of a real whiteboard after a brainstorming session. [RATIO] aspect ratio.

=== TOP TITLE BAR ===
Hand-written bold title: "[TITLE]"
Below it: "[SUBTITLE]" with yellow highlight on [KEY WORDS]
Cyan marker underline stroke under the main title.
TOP-RIGHT: "AiwithDhruv" in bold cyan marker inside a hand-drawn rounded rectangle badge. Smaller text below: "youtube | github | linkedin"

=== LEFT COLUMN — "[LEFT HEADER]" ===
Header: "[LEFT HEADER]" inside a hand-drawn box
[CHECKLIST OR CONTENT — each item with a small hand-drawn logo]

=== CENTER — "[CENTER HEADER]" (largest section) ===
Header: "[CENTER HEADER]" with a circle around it

Flowchart with boxes connected by hand-drawn arrows:
[BOX 1]: "[STEP 1]" — subtitle: "[DESCRIPTION]"
↓ arrow
[BOX 2]: "[STEP 2]" — subtitle: "[DESCRIPTION]"
↓ arrow
[BOX 3]: "[STEP 3]" with small sketched icons: [ICONS LIST]
↓ arrow
[BOX 4]: "[FINAL STEP]" with [BADGE/INDICATOR]

=== FLASH CARDS scattered around like sticky notes, tilted at slight angles ===

[COLOR 1] sticky note (tilted, near [POSITION]):
"[FEATURE 1 TITLE]"
"[DETAIL LINE 1]"
"[DETAIL LINE 2]"
Small [ICON] doodle

[COLOR 2] sticky note (tilted, near [POSITION]):
"[FEATURE 2 TITLE]"
"[DETAIL LINE 1]"
"[DETAIL LINE 2]"
Small [ICON] doodle

[Repeat for 3-5 flash cards total]

Some flash cards have paper clip or tape marks holding them on.

=== RIGHT COLUMN — "[RIGHT HEADER]" ===
Header: "[RIGHT HEADER]"
[MOCKUP OR VISUAL — browser window, app screen, dashboard, etc.]
[CONTENT INSIDE the mockup — never leave blank]

=== BOTTOM LEFT — [DIAGRAM TYPE] ===
[Architecture/system diagram with boxes, logos, and arrows]
Labels on connections: [LABELS]

=== BOTTOM CENTER — Stats Row ===
Three items in a row, each circled with yellow highlight:
"[STAT 1]"    "[STAT 2]"    "[STAT 3]"
Small star doodles around the stats

=== BOTTOM RIGHT — Author + Branding ===
"AiwithDhruv" with cyan lightning bolt
"@aiwithdhruv" and "github.com/aiagentwithdhruv"
"AD" monogram in a hand-drawn circle

=== OPTIONAL: Author Portrait ===
[Include ONLY if generating separately or if Gemini doesn't flag it]
Clean sketch portrait of the author in same marker style. Short hair, glasses,
trimmed beard, black t-shirt with "AiwithDhruv" in cyan. Holding a blue marker
pen pointing at the diagram. Speech bubble: "[CATCHPHRASE]"
Size: 15-18% of image height, bottom-right corner, overlapping paper edge.

=== AMBIENT DETAILS ===
- Coffee ring stain near bottom-left (subtle)
- Paper clips on 1-2 flash cards
- Tape marks on corners of some sticky notes
- Blue pen lying on the desk
- Small doodle arrows and stars in empty spaces
- Wooden desk texture at all edges
- Faint "AiwithDhruv" watermark diagonally across center in light grey

=== STYLE — CRITICAL ===
- Real black marker on white paper — authentic hand-drawn feel
- Slightly imperfect handwriting but always readable
- Cyan for headers, connections, branding
- Yellow highlighter for numbers and stats
- Pastel colored sticky notes at slight angles
- Small recognizable tech logos hand-drawn next to every tool
- Everything hand-drawn — NO computer fonts
- Clean enough to read on a phone screen
```

## Platform-Specific Ratios

| Platform | Ratio | Notes |
|----------|-------|-------|
| GitHub README | 16:9 | Landscape, max detail |
| YouTube thumbnail | 16:9 | Bold title, less detail |
| LinkedIn post | 4:5 | Vertical, larger text |
| Instagram post | 1:1 or 4:5 | Square or vertical |
| Twitter/X | 16:9 | Landscape, punchy |
| Presentation slide | 16:9 | Clean, minimal flash cards |

## Flash Card Color Guide

| Color | Use For |
|-------|---------|
| Yellow | Main feature / hero capability |
| Light Blue | Tech/skills/open source |
| Pink/Coral | Data/memory/persistence |
| Light Green | Products/content/quantity |
| Light Purple | Integrations/webhooks/connections |

## Examples Generated

### 1. AiwithDhruv Portfolio (the original)
- **Title:** "Build a Stunning Portfolio with AI"
- **Subtitle:** "Zero Code. Zero Cost. ~3 Hours."
- **Left:** Prerequisites checklist (Node.js, Claude Code, Supabase, Vercel, Google AI)
- **Center:** Build flow (Prompt → Claude Code → 12 Components → Deploy)
- **Right:** Browser mockup of aiwithdhruv.com with sections labeled
- **Flash cards:** AI Voice, 39 Skills, Visitor Memory, 10 Products, Contact→n8n
- **Stats:** $0/month, ~3 hours, 0 lines of code
- **Result:** Generated via Gemini, used as GitHub README hero image

## Process (Every Time)

1. **Identify the project** — what are we explaining?
2. **Extract the flow** — what are the 3-5 key steps?
3. **Pick 4-5 features** for flash cards
4. **Identify tech stack** for logos
5. **Design the mockup** — what does the result look like?
6. **Pick the stats** — 3 impressive numbers
7. **Fill the template** — replace all [BRACKETS]
8. **Set the ratio** — 16:9 for GitHub, 4:5 for social
9. **Generate in Gemini** — paste the prompt
10. **If portrait needed** — generate separately and composite

## Author Portrait Workaround

Gemini sometimes flags person descriptions. If it fails:
1. Generate the diagram WITHOUT the portrait
2. Generate portrait separately with this prompt:
```
Clean editorial ink sketch portrait on white paper. A confident tech
founder with short hair, trimmed beard, and round glasses, wearing a
black t-shirt with "AiwithDhruv" in cyan. Holding a blue marker pen,
pointing forward. Speech bubble: "[TEXT]". Professional editorial
illustration style, black ink, clean lines, minimal shading. White
background. Half body from waist up.
```
3. Composite in any image editor (Canva, Preview, Photoshop)

## Composable With
- `thumbnail-generator` — for cinematic photo-style images
- `nano-banana-images` — for hyper-realistic photos via fal.ai
- `excalidraw-diagram` — for editable technical diagrams
- `excalidraw-visuals` — for rendered PNG visuals
- `video-edit` — for video thumbnails using the diagram

## Schema

### Inputs
| Name | Type | Required | Description |
|------|------|----------|-------------|
| `project` | string | Yes | What project/product to diagram |
| `title` | string | Yes | Main title text |
| `subtitle` | string | Yes | Subtitle with key numbers |
| `steps` | array | Yes | 3-5 build/process steps |
| `flash_cards` | array | Yes | 4-5 feature highlights |
| `tech_stack` | array | Yes | Tools/tech with logos |
| `stats` | array | Yes | 3 impressive numbers |
| `mockup` | string | Yes | What the result looks like |
| `ratio` | string | No | '16:9' (default) or '4:5' |
| `include_portrait` | boolean | No | Include author sketch (default: false) |

### Outputs
| Name | Type | Description |
|------|------|-------------|
| `prompt` | string | Copy-paste prompt for Gemini |
| `portrait_prompt` | string | Separate portrait prompt (if needed) |

### Credentials
None required (generates prompts, not images)

### Cost
Free (prompt generation only — image generation is free via Gemini)
