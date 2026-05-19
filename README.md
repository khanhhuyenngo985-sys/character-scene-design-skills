# Character + Scene Design Skills

This repository contains reusable skills for designing production-ready characters, scenes, props, visual assets, and prompts for image and video generation.

The goal is not just to make attractive pictures. These skills help turn ideas into stable assets: character identity, body proportion, face anchors, wardrobe states, prop geometry, relationship pressure, scene layout, blocking, continuity, and model-ready prompts.

## What This Is For

Use these skills for many kinds of visual projects:

- animation characters and recurring mascots
- game heroes, NPCs, bosses, creatures, and factions
- film, short film, series, and commercial characters
- fantasy, sci-fi, historical, wuxia, modern, stylized, or realistic roles
- live-action casting assets and wardrobe fitting boards
- character sheets, turnaround sheets, expression sheets, prop callouts, and outfit variants
- finished multi-panel character sheets with hero portrait, turnaround, expressions, wardrobe states, prop details, action/skill panels, and palette
- reusable scenes, power-space layouts, blocking plans, and video reference boards
- script-to-asset manifests that separate `SCENE_`, `CHAR_`, and `PROP_` cards before prompting

Short-drama, overseas casting, and vertical-video workflows are supported as optional specializations, not the default scope.

## Quick Start

```text
Use character-design to create a production-ready character sheet for a fantasy courier: identity anchors, height/proportion lock, face anchors, wardrobe states, signature prop geometry, expressions, action poses, and video-readiness QC.
```

```text
Use character-design to redesign this reference character while preserving the original body shape, height, mouth, hair, costume category, and waist prop. Start with a proportion lock before making the final sheet.
```

```text
Use scene-design to create a reusable scene pack for a royal archive, including layout, entrances/exits, actor zones, light/material anchors, blocking lanes, and continuity notes for image/video generation.
```

```text
Use character-design and scene-design to turn this script into an asset manifest: scene cards, character cards, prop cards, global style lock, and QC checks for material, era/world consistency, body proportion, and prop geometry.
```

## Main Skills

| Skill | Use It For | Typical Outputs |
| --- | --- | --- |
| `character-design` | Characters, casts, character sheets, height/proportion locks, face anchors, wardrobe states, prop anchors, relationship matrices, video-readiness checks | Character packet, proportion base, W0 turnaround, expression sheet, wardrobe ladder, prompt anchors |
| `scene-design` | Scene systems, environment boards, power-space architecture, blocking lanes, scene states, continuity anchors, image/video scene prompts | Scene card, layout logic, reusable scene pack, blocking plan, video audition prompt |

Both skills include `references/full-asset-master-v3.md`, a shared production gate for separating scene, character, and prop assets before model-specific prompts are written.

## Character Workflow

```text
Character purpose
-> Character DNA
-> Height / proportion lock
-> Face and permanent prop lock
-> W0 front / side / back turnaround
-> Wardrobe state ladder
-> Expressions and action poses
-> Final character sheet
-> Motion audition / video-readiness QC
```

Quality checks:

- The character is memorable, not just pretty.
- Height and body proportion are locked before a final sheet is generated.
- Front, side, and back views look like the same physical asset rotated.
- Wardrobe variants do not change the face, body width, leg length, height, or permanent props.
- Signature props have clear geometry and do not drift into generic objects.
- Multi-shot prompts preserve identity while allowing visible state changes.

## Scene Workflow

```text
Story / use case
-> Scene function
-> Layout and entrances / exits
-> Actor zones and blocking
-> Material, light, color, and prop anchors
-> Scene states
-> Image reference prompt
-> Video audition / continuity QC
```

Quality checks:

- The scene supports action, conflict, emotion, or information flow.
- Entrances, exits, sightlines, foreground/midground/background, and actor zones are clear.
- Fixed anchors make the scene reusable across shots.
- State changes are visible through light, props, residue, damage, weather, or arrangement.
- The scene can be used by the target image/video model without relying on hidden exposition.

## Full Asset Workflow

```text
Script / concept
-> Global image type, genre, era, and style lock
-> Asset manifest: SCENE_ / CHAR_ / PROP_
-> Scene seven-layer cards
-> Character body / face / costume / permanent anchor cards
-> Prop four-view cards
-> Model-specific prompts
-> QC for separation, material, era/world, proportion, prop geometry, and color
```

## Optional Specializations

The repository includes deeper references for specific workflows, such as:

- live-action casting and wardrobe-fitting assets
- vertical short-drama cast and scene systems
- full scene / character / prop asset production
- bone / face structure consistency
- genre cast packs and relationship matrices
- traditional / historical / stylized visual design
- prompt templates for different image and video tools

Open these references only when the project needs that specialization. For general character or scene design, start with the skill `SKILL.md` files.

## Structure

```text
skills/
├── character-design/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   ├── SECTIONS/
│   └── references/
└── ...

.agents/skills/
├── character-design/
└── scene-design/
```

The `skills/` directory is the general skill collection. The `.agents/skills/` directory is kept for agent-style installs and legacy workflows.

## Install

Copy the skill you want into your local agent skills directory:

```bash
mkdir -p ~/.agents/skills
cp -R skills/character-design ~/.agents/skills/
```

For Claude-style skill directories:

```bash
mkdir -p ~/.claude/skills
cp -R skills/character-design ~/.claude/skills/
```

## Reading Principles

- Start with `SKILL.md`; it is the lightweight runtime entry.
- Read `references/*.md` or `SECTIONS/*.md` only when the task needs deeper detail.
- Do not load full manuals by default.
- Treat specialized short-drama references as optional, not the default path.

## Git Workflow

- Use feature branches and pull requests.
- `main` is protected: no force push and no direct deletion.
- CI/status checks may vary by downstream repository.

## License

Released under the MIT License unless a downstream package states otherwise.
