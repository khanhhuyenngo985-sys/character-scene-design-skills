# Scene Design Skill

`scene-design` is a general AI-image and AI-video scene design skill for designing, revising, diagnosing, and prompting stable scenes and environment assets.

Use it for:

- scene cards and environment packets
- full asset-library scene cards that stay separate from character and prop cards
- spatial logic, actor zones, entrances, exits, and blocking support
- fixed scene anchors for AI-video continuity
- light, color, material, atmosphere people, and camera opportunities
- reducing scene drift across storyboard, image, and video workflows

## Structure

```text
scene-design/
├── SKILL.md
├── README.md
├── agents/openai.yaml
└── references/
    ├── full-manual.md
    ├── full-asset-master-v3.md
    └── live-action-shortdrama-scene-system.md
```

## How It Loads

Read `SKILL.md` first. It is the runtime entry and should be enough for most scene design work.

Open `references/full-asset-master-v3.md` when turning a script or concept into coordinated scene, character, and prop assets.

Open `references/full-manual.md` only when the task needs deeper method detail, such as architecture style, space sequence, lighting systems, environmental storytelling, or multi-scene continuity.

## Typical Request

```text
Use scene-design to create a reusable scene packet for a rainy night market chase.
```

Expected output:

- scene tag
- narrative task
- world rule or pressure
- space type, layout, zones, entrance, and exit
- fixed anchors and narrative props
- atmosphere people when they help scale and world occupancy
- light direction, color, material, and camera opportunities
- before/after continuity and forbidden drift

## License

MIT.
