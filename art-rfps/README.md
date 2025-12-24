---
title: Art RFPs - Visual Asset Pipeline
version: 1.0.0
tags:
  - art
  - commissioning
  - illustration
  - ai-art
  - rfp
---

# 🎨 Art RFPs

**Visual Asset Pipeline: From AI Placeholder to Human Art**

*~collaborating with the creative pack~* 🐕🎨

This directory manages visual assets for Pack Protocols, including a system for generating AI placeholder art and commissioning human artists to create polished final versions.

---

## Philosophy

Pack Protocols benefits from visual aids—diagrams, illustrations, icons—that make frameworks more accessible. We use a two-stage approach:

1. **AI Placeholders** — Quick generation for prototyping and documentation
2. **Human Commissions** — Community artists create final versions

This approach:
- Speeds initial development
- Provides clear specs for artists
- Creates opportunities for community artists
- Ensures human creativity in final product

---

## AI Placeholder Specifications

When generating placeholder art, document:

```yaml
# Example AI art spec
asset_id: fire-triangle-diagram-001
description: "Diagram showing the Fire Triangle with Fuel, Oxygen, and Heat at vertices"
intended_use: documentation, presentations
dimensions: 800x600px
style: line art, minimal, professional
colors:
  - "#F5A623" # Fuel/SDCoLab gold
  - "#4A90D9" # Oxygen/SDCAP blue  
  - "#D0021B" # Heat/Community red
elements:
  - triangle shape
  - labels at each vertex
  - fire icon in center
ai_tool: Claude/DALL-E/Midjourney
generation_prompt: "Simple line diagram of fire triangle..."
placeholder_status: true
human_replacement_needed: true
```

---

## Commissioning Template

When ready to commission human art:

### Request for Proposal (RFP)

```markdown
## Art Commission Request

**Asset ID:** [from spec]
**Project:** Pack Protocols

### Description
[What the artwork depicts]

### Technical Requirements
- **Dimensions:** [size in pixels]
- **Format:** [PNG, SVG, etc.]
- **Color Palette:** [hex codes]
- **Style:** [description]

### Reference
- **AI Placeholder:** [link to placeholder image]
- **Additional References:** [links]

### Context
[How this will be used, where it will appear]

### Deliverables
- Source file (AI, PSD, etc.)
- Web-ready export
- Print-ready export (if applicable)

### Timeline
- **Submission Deadline:** [date]
- **Review Period:** [dates]
- **Final Delivery:** [date]

### Compensation
[Payment terms, amount, method]

### Rights
- License: CC BY-SA 4.0
- Attribution: [how artist will be credited]

### Contact
[How to submit questions, proposals]
```

---

## Asset Registry

Track all visual assets:

| Asset ID | Description | Status | Artist | Location |
|----------|-------------|--------|--------|----------|
| fire-triangle-001 | Fire Triangle diagram | Placeholder | AI | /assets/diagrams/ |
| pack-dynamics-001 | Pack states diagram | Placeholder | AI | /assets/diagrams/ |
| cerberus-logo-001 | Three-headed dog logo | Final | [Artist] | /assets/branding/ |

---

## Artist Guidelines

For artists interested in creating Pack Protocols artwork:

### Style Guidelines

- **Tone:** Warm, professional, approachable
- **Character:** Naturalistic dog imagery preferred over cartoon
- **Metaphor:** Fire and dog themes throughout
- **Avoid:** Overly corporate, cold, or generic stock art feeling

### Submission Process

1. Review the RFP
2. Ask clarifying questions
3. Submit proposal with:
   - Portfolio samples
   - Proposed approach
   - Timeline
   - Rate
4. If selected, create initial concept
5. Revisions based on feedback
6. Final delivery

### Compensation

We compensate artists fairly. Rates discussed per project. Community members may contribute pro bono; this is welcomed but never expected.

### Attribution

All artists credited in:
- Asset metadata
- CREDITS.md file
- Context where art appears (where practical)

---

## Directory Structure

```
/art-rfps
  README.md           # This file
  COMMISSIONING.md    # Full commissioning guide
  /specs              # AI placeholder specifications
  /rfps               # Active commission requests
  /assets             # Final approved artwork
  CREDITS.md          # Artist attributions
```

---

## Current Needs

Assets we'd love human versions of:

1. **Fire Triangle Diagram** — Clean, professional version
2. **Pack States Illustration** — Four states (running well, wild, friction, stuck)
3. **Three Cerberus Heads** — Shepherd, Guide, Companion
4. **Growth Spiral** — Project → Party → Practice

Interested? See current RFPs in `/rfps` or contact us.

---

## License

All commissioned artwork for Pack Protocols is licensed **CC BY-SA 4.0** unless otherwise negotiated. Artists retain right to display work in portfolios.

---

*~creating beauty together~* 🎨🐕
