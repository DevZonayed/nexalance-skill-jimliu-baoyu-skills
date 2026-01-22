---
name: first-time-setup
description: First-time setup flow for baoyu-xhs-images preferences
---

# First-Time Setup

## Overview

When no EXTEND.md is found, guide user through preference setup.

## Setup Flow

```
No EXTEND.md found
        │
        ▼
┌─────────────────────┐
│ AskUserQuestion     │
│ (all questions)     │
└─────────────────────┘
        │
        ▼
┌─────────────────────┐
│ Create EXTEND.md    │
└─────────────────────┘
        │
        ▼
    Continue to Step 1
```

## Questions

Use single AskUserQuestion with multiple questions (AskUserQuestion auto-adds "Other" option):

### Question 1: Watermark

```
header: "Watermark"
question: "Enable watermark on generated images?"
options:
  - label: "Enabled"
    description: "Add watermark to all images"
  - label: "Disabled"
    description: "No watermark (can enable later)"
```

### Question 2: Watermark Content (if enabled)

```
header: "Content"
question: "What text for your watermark?"
options:
  - label: "@username"
    description: "Your XHS handle (replace 'username')"
  - label: "Custom text"
    description: "Enter your own text"
```

### Question 3: Watermark Position (if enabled)

```
header: "Position"
question: "Where to place watermark?"
options:
  - label: "bottom-right"
    description: "Lower right corner (most common)"
  - label: "bottom-left"
    description: "Lower left corner"
  - label: "bottom-center"
    description: "Bottom center"
  - label: "top-right"
    description: "Upper right corner"
```

### Question 4: Preferred Style

```
header: "Style"
question: "Default visual style preference?"
options:
  - label: "cute"
    description: "Sweet, adorable - classic XHS aesthetic"
  - label: "notion"
    description: "Minimalist hand-drawn, intellectual"
  - label: "None"
    description: "Auto-select based on content"
```

### Question 5: Save Location

```
header: "Save"
question: "Where to save preferences?"
options:
  - label: "Project"
    description: ".baoyu-skills/ (this project only)"
  - label: "User"
    description: "~/.baoyu-skills/ (all projects)"
```

## Save Locations

| Choice | Path | Scope |
|--------|------|-------|
| Project | `.baoyu-skills/baoyu-xhs-images/EXTEND.md` | Current project |
| User | `~/.baoyu-skills/baoyu-xhs-images/EXTEND.md` | All projects |

## After Setup

1. Create directory if needed
2. Write EXTEND.md with frontmatter
3. Confirm: "Preferences saved to [path]"
4. Continue to Step 1

## EXTEND.md Template

```yaml
---
version: 1
watermark:
  enabled: [true/false]
  content: "[user input]"
  position: [selected position]
  opacity: 0.7
preferred_style:
  name: [selected style or null]
  description: ""
preferred_layout: null
language: null
custom_styles: []
---
```

## Modifying Preferences Later

Users can edit EXTEND.md directly or run setup again:
- Delete EXTEND.md to trigger setup
- Edit YAML frontmatter for quick changes
- Full schema: `references/preferences-schema.md`
