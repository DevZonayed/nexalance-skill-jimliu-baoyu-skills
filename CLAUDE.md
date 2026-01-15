# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Claude Code marketplace plugin providing AI-powered content generation skills. Skills use Gemini Web API (reverse-engineered) for text/image generation and Chrome CDP for browser automation.

## Architecture

```
skills/
├── baoyu-gemini-web/          # Core: Gemini API wrapper (text + image gen)
├── baoyu-xhs-images/          # Xiaohongshu infographic series (1-10 images)
├── baoyu-cover-image/         # Article cover images (2.35:1 aspect)
├── baoyu-slide-deck/          # Presentation slides with outlines
├── baoyu-article-illustrator/ # Smart illustration placement
├── baoyu-post-to-x/           # X/Twitter posting automation
└── baoyu-post-to-wechat/      # WeChat Official Account posting
```

Each skill contains:
- `SKILL.md` - YAML front matter (name, description) + documentation
- `scripts/` - TypeScript implementations
- `prompts/system.md` - AI generation guidelines (optional)

## Running Skills

All scripts run via Bun (no build step):

```bash
npx -y bun skills/<skill>/scripts/main.ts [options]
```

Examples:
```bash
# Text generation
npx -y bun skills/baoyu-gemini-web/scripts/main.ts "Hello"

# Image generation
npx -y bun skills/baoyu-gemini-web/scripts/main.ts --prompt "A cat" --image cat.png

# From prompt files
npx -y bun skills/baoyu-gemini-web/scripts/main.ts --promptfiles system.md content.md --image out.png
```

## Key Dependencies

- **Bun**: TypeScript runtime (via `npx -y bun`)
- **Chrome**: Required for `baoyu-gemini-web` auth and `baoyu-post-to-x` automation
- **No npm packages**: Self-contained TypeScript, no external dependencies

## Authentication

`baoyu-gemini-web` uses browser cookies for Google auth:
- First run opens Chrome for login
- Cookies cached in data directory
- Force refresh: `--login` flag

## Plugin Configuration

`.claude-plugin/marketplace.json` defines plugin metadata and skill paths. Version follows semver.

## Adding New Skills

**IMPORTANT**: All skills MUST use `baoyu-` prefix to avoid conflicts when users import this plugin.

1. Create `skills/baoyu-<name>/SKILL.md` with YAML front matter
   - Directory name: `baoyu-<name>`
   - SKILL.md `name` field: `baoyu-<name>`
2. Add TypeScript in `skills/baoyu-<name>/scripts/`
3. Add prompt templates in `skills/baoyu-<name>/prompts/` if needed
4. Register in `marketplace.json` plugins[0].skills array as `./skills/baoyu-<name>`

## Code Style

- TypeScript throughout, no comments
- Async/await patterns
- Short variable names
- Type-safe interfaces
