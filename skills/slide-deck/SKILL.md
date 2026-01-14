---
name: slide-deck
description: Generate professional slide deck outlines from content. Creates comprehensive, designer-ready outlines with style instructions, narrative structure, and detailed slide specifications. Use when user asks to "create slides", "make a presentation", "generate deck", or "slide deck outline".
---

# Slide Deck Outline Generator

Transform content into professional, designer-ready slide deck outlines with comprehensive style instructions and narrative structure.

## Usage

```bash
# From markdown file
/slide-deck path/to/article.md

# With style preference
/slide-deck path/to/article.md --style corporate
/slide-deck path/to/article.md --style playful
/slide-deck path/to/article.md --style technical

# With audience specification
/slide-deck path/to/article.md --audience beginners
/slide-deck path/to/article.md --audience executives

# With language
/slide-deck path/to/article.md --lang zh
/slide-deck path/to/article.md --lang en

# Direct content input
/slide-deck
[paste content]
```

## Options

| Option | Description |
|--------|-------------|
| `--style <name>` | Visual style preset (see Style Gallery) |
| `--audience <type>` | Target audience level |
| `--lang <code>` | Output language (en, zh, etc.) |
| `--slides <number>` | Target slide count (max 20) |

## Style Gallery

### 1. `editorial` (Default)
Clean, sophisticated, minimalist
- **Aesthetic**: High-end journal, architectural blueprints
- **Colors**: Off-white background, dark slate text, blue accents
- **Best for**: Thought leadership, research presentations

### 2. `corporate`
Professional, trustworthy, polished
- **Aesthetic**: Clean lines, structured layouts, business-appropriate
- **Colors**: Navy, white, subtle gold accents
- **Best for**: Business presentations, investor decks, reports

### 3. `technical`
Precise, data-driven, analytical
- **Aesthetic**: Blueprint style, schematic diagrams, grid layouts
- **Colors**: Dark backgrounds, cyan/green accents, monospace elements
- **Best for**: Technical documentation, engineering presentations

### 4. `playful`
Bold, energetic, engaging
- **Aesthetic**: Dynamic shapes, vibrant colors, creative layouts
- **Colors**: Bright primaries, gradients, contrasting pops
- **Best for**: Creative pitches, educational content, workshops

### 5. `minimal`
Ultra-clean, zen-like, focused
- **Aesthetic**: Maximum whitespace, single focal points, elegant typography
- **Colors**: Black, white, single accent color
- **Best for**: Keynotes, philosophical content, product launches

### 6. `storytelling`
Narrative-driven, cinematic, immersive
- **Aesthetic**: Full-bleed imagery, dramatic typography, chapter-like flow
- **Colors**: Rich, moody palettes with high contrast
- **Best for**: Case studies, journey narratives, brand stories

## Audience Presets

| Audience | Approach |
|----------|----------|
| `beginners` | Step-by-step, more context, simpler visuals |
| `intermediate` | Balanced detail, some assumed knowledge |
| `experts` | Dense information, technical depth, less hand-holding |
| `executives` | High-level insights, key metrics, strategic focus |
| `general` | Accessible language, broad appeal, clear takeaways |

## File Management

Save output to same directory as source:

```
path/to/
├── article.md
└── slide-deck/
    └── outline.md
```

Or to current directory if no source path:

```
./
└── slide-deck-outline.md
```

## Workflow

### Step 1: Analyze Content

Extract from source material:
- Core narrative and key messages
- Important data points and statistics
- Logical flow and structure
- Target audience signals

### Step 2: Generate Style Instructions

Create a global `STYLE_INSTRUCTIONS` block based on content topic:

```markdown
<STYLE_INSTRUCTIONS>
Design Aesthetic: [Overall style description]
Background Color: [Description and Hex Code]
Primary Font: [Font name for Headlines]
Secondary Font: [Font name for Body copy]
Color Palette:
  Primary Text Color: [Hex Code]
  Primary Accent Color: [Hex Code]
Visual Elements: [Lines, shapes, imagery style, etc.]
</STYLE_INSTRUCTIONS>
```

### Step 3: Create Slide Outline

Structure each slide with 4 required sections:

```markdown
## Slide N: [Descriptive Title]

// NARRATIVE GOAL
[Storytelling purpose within the overall arc]

// KEY CONTENT
Headline: [Main message - narrative, not "Title: Subtitle" format]
Sub-headline: [Supporting context]
Body:
- [Key point 1 with specific data from source]
- [Key point 2 with specific data from source]
- [Key point 3 with specific data from source]

// VISUAL
[Detailed description of imagery, charts, graphics, or abstract visuals]

// LAYOUT
[Composition, hierarchy, spatial arrangement, focus points]
```

### Step 4: Ensure Structure

Required slide structure:
1. **Slide 1**: Cover Slide (poster-style, heroic typography)
2. **Slides 2-N-1**: Content slides (consistent internal style)
3. **Slide N**: Back Cover (closing statement, not "Thank You")

### Step 5: Output Complete Outline

```markdown
# Slide Deck Outline: [Topic]

**Source**: [source file or "Direct input"]
**Style**: [selected style]
**Audience**: [target audience]
**Language**: [output language]
**Slide Count**: [N slides]

---

<STYLE_INSTRUCTIONS>
[Complete style block]
</STYLE_INSTRUCTIONS>

---

## Slide 1: [Cover]
[4 sections]

## Slide 2: [First Content]
[4 sections]

...

## Slide N: [Back Cover]
[4 sections]
```

## Style Reference Details

### editorial
```
Design Aesthetic: Clean, sophisticated, minimalist editorial inspired by architectural blueprints and high-end technical journals
Background Color: Subtle textured off-white #F8F7F5
Primary Font: Neue Haas Grotesk Display Pro (bold headlines)
Secondary Font: Tiempos Text (body copy, annotations)
Primary Text Color: Dark slate grey #2F3542
Primary Accent Color: Intelligent blue #007AFF
Visual Elements: Thin precise line work, schematic diagrams, clean vectors, spacious layouts
```

### corporate
```
Design Aesthetic: Professional, trustworthy, structured business presentation
Background Color: Clean white #FFFFFF with navy accents
Primary Font: Inter (headlines)
Secondary Font: Source Sans Pro (body)
Primary Text Color: Navy #1E3A5F
Primary Accent Color: Gold #C9A227
Visual Elements: Clean charts, professional icons, structured grids, subtle shadows
```

### technical
```
Design Aesthetic: Blueprint-style, precise, data-driven analytical presentation
Background Color: Dark charcoal #1A1A2E
Primary Font: JetBrains Mono (headlines)
Secondary Font: IBM Plex Sans (body)
Primary Text Color: Light gray #E8E8E8
Primary Accent Color: Cyan #00D4FF
Visual Elements: Grid overlays, circuit patterns, data visualizations, monospace code blocks
```

### playful
```
Design Aesthetic: Bold, energetic, creative with dynamic visual interest
Background Color: Warm white #FFFDF7
Primary Font: Poppins (headlines)
Secondary Font: Nunito (body)
Primary Text Color: Deep purple #4A1D96
Primary Accent Color: Vibrant coral #FF6B6B
Visual Elements: Rounded shapes, gradients, illustrations, dynamic compositions, bright pops
```

### minimal
```
Design Aesthetic: Ultra-clean, zen-like focus with elegant restraint
Background Color: Pure white #FFFFFF
Primary Font: Helvetica Neue (headlines)
Secondary Font: Garamond (body)
Primary Text Color: Pure black #000000
Primary Accent Color: Single accent (content-derived)
Visual Elements: Maximum whitespace, single focal points, hairline rules, elegant typography
```

### storytelling
```
Design Aesthetic: Cinematic, narrative-driven with immersive visual flow
Background Color: Rich charcoal #2D2D2D or full-bleed imagery
Primary Font: Playfair Display (headlines)
Secondary Font: Lora (body)
Primary Text Color: Warm white #FAF9F6
Primary Accent Color: Warm gold #D4AF37
Visual Elements: Full-bleed photos, dramatic typography, chapter markers, emotional imagery
```

## Output Example

```markdown
# Slide Deck Outline: AI Agent Automation Guide

**Source**: use-agents-guide/article.md
**Style**: technical
**Audience**: intermediate
**Language**: English
**Slide Count**: 12 slides

---

<STYLE_INSTRUCTIONS>
Design Aesthetic: Blueprint-style technical presentation with analytical precision
Background Color: Dark charcoal #1A1A2E
Primary Font: JetBrains Mono
Secondary Font: IBM Plex Sans
Primary Text Color: #E8E8E8
Primary Accent Color: #00D4FF
Visual Elements: Grid overlays, data visualizations, schematic diagrams
</STYLE_INSTRUCTIONS>

---

## Slide 1: Cover

// NARRATIVE GOAL
Set the stage with a bold, attention-grabbing statement that frames the entire presentation's thesis.

// KEY CONTENT
Headline: "90% of your work should be agent-generated"
Sub-headline: A practical guide to automation that actually works

// VISUAL
Abstract visualization of human-AI collaboration: a stylized figure working alongside flowing data streams and geometric AI representation.

// LAYOUT
Poster-style full-bleed. Headline dominates upper 60%, visual anchors bottom 40%. No clutter, pure impact.

---

## Slide 2: The Reality Check

// NARRATIVE GOAL
Ground the audience by acknowledging the hype while establishing credibility through real experience.

// KEY CONTENT
Headline: Eight months of daily agent use revealed what works and what doesn't
Body:
- 8 months of Claude Code for writing, not just coding
- Hundreds of hours of experimentation
- Focus on non-engineering tasks: blog posts, grant proposals, meta reviews

// VISUAL
Timeline graphic showing the journey from experimentation to practical insights, with key milestones marked.

// LAYOUT
Left third: timeline visual. Right two-thirds: key points with subtle data callouts.

...
```

## Notes

- Maximum 20 slides per deck
- Every data point must trace to source material
- Avoid AI-generated clichés ("It wasn't just X, it was Y")
- Use narrative headlines, not "Title: Subtitle" format
- Cover and Back Cover should be visually distinct (poster-style)
- Back Cover should be meaningful closure, not "Thank You" or "Questions?"
- Designer will not have access to source - include all necessary details
