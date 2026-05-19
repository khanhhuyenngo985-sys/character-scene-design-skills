# Finished Character Sheet Prompt / 成品角色图提示词

Use this when the user asks for 成品角色图, 角色设定图, character concept sheet, character design board, final character sheet, GPT Image 2 character sheet, or wants an image like a game / animation / film character bible page with multiple panels.

## Core Rule

A finished character sheet is not a single portrait. It is a production board that proves the character can be reused.

It must show:

- identity: name, role, world, age or apparent age, height / proportion
- locked body: front / side / back views that match one physical asset
- locked face: close-up and expression range
- locked costume: default outfit plus variants or states
- locked permanent props: geometry, attachment side, material, front/back visibility
- performance: posture, behavior, action or skill vocabulary
- material / palette: color and touchable costume/prop surfaces

If the body, face, or permanent prop has not passed base QC, produce a base-lock prompt first. Do not pretend a dense final sheet will fix an unstable design.

## Required Layout

For GPT Image 2, use a wide design-board layout by default: 16:9, 2:1, or another wide ratio the user requests.

Default module map:

| Module | Required content |
| --- | --- |
| Title / identity panel | character name, alias / role, concise basic info, height and body ratio |
| Hero portrait | large bust or 45-degree close-up showing face, hair, skin texture, mouth, expression |
| Turnaround | full-body front, side, and back views in the default outfit, same baseline and same scale |
| Height / proportion lock | net height, styled max height if needed, head ratio, width-height ratio, leg ratio |
| Expression row | 4-8 readable expressions that preserve face shape and mouth |
| Wardrobe / state variants | 3-4 outfits or story states, all preserving body shape and permanent anchors |
| Prop detail panel | permanent wearable props and key tools, with shape, material, side, attachment, and close-up |
| Action / behavior panel | 2-4 habitual actions, posture signatures, combat / work / comedic / ritual moves |
| Ability / skill panel | optional for genre characters; use tools, powers, job skills, or narrative functions |
| Material / palette strip | costume fabric, metal, wood, leather, paper, skin/fur/clay/etc. and color anchors |

Keep the page readable. If the requested modules are too many, split into:

1. identity + turnaround sheet
2. expressions + wardrobe sheet
3. prop + action / skill sheet

## Text Policy

- Important headings and labels may be exact Chinese.
- Keep visible text short: names, section labels, height numbers, outfit names, expression labels.
- Do not ask the model to render long biographies or dense paragraphs.
- If long lore is needed, write it outside the image prompt as production notes.

Useful Chinese section labels:

```text
角色名, 基础档案, 身高比例, 正面, 侧面, 背面, 面部特写, 经典表情, 服装状态, 道具细节, 习惯动作, 核心技能, 材质色板
```

## Proportion Protection

Add a strong body lock whenever the role has a nonstandard body:

```text
All panels depict the same physical character asset. Preserve exact body type, height, head ratio, body width, leg length, waist line, neck visibility, hand size, foot baseline, hairstyle volume, costume category, and permanent prop ownership across every panel.
```

For short / round / stylized characters, include:

```text
Do not slim, stretch, mature, beautify, or normalize the body. Height ruler and labels annotate the existing body; they must not make the character taller. Full-body views keep the same wide silhouette and short legs.
```

For front / side / back:

```text
The turnaround must look like one puppet rotated in place: same head size, same body width, same sleeve length, same hem height, same strap path, same prop side, same bag side, same hair mass, same foot baseline.
```

## Prompt Packet Shape

```text
【Prompt ID】CHAR_[name]_final_sheet_v##
【Target】GPT Image 2
【Subtype】character-concept
【Output use】final reusable character design sheet / asset bible page
【Aspect ratio】wide 16:9 or 2:1
【Reference binding】source image(s), what to preserve, what may change
【Character identity】name, role, world, narrative function
【Body / proportion lock】height, head ratio, width-height ratio, leg ratio, protected silhouette
【Face / hair lock】face shape, eyes, brows, nose, mouth, skin, hair, headwear
【Costume system】inner layer, main layer, outer layer, waist, lower body, footwear, materials
【Permanent props】shape, side, attachment, material, front/back behavior
【Layout modules】title, hero portrait, turnaround, expressions, wardrobe states, props, actions/skills, palette
【Text policy】short readable Chinese labels only; no long paragraphs
【Style】project visual style, render finish, background board style
【Consistency anchors】3-8 must-keep anchors
【Avoid】single portrait, poster, beauty shot, random scene background, inconsistent views, stretched body, missing mouth, prop drift
【QC】front/side/back consistency, height/proportion, mouth visible, prop readable, all panels same character
```

## Paste-Ready GPT Image 2 Shape

```text
GPT Image 2 image prompt.
Type: character-concept.
Use: final reusable character design sheet / asset bible page, wide 16:9.
Create a complete multi-panel character sheet, not a single portrait, not a poster, not a scene illustration.

Reference binding: [reference image / existing character packet]. Preserve [body, face, hair, costume category, permanent props]. May redesign [allowed changes].

Character: [name], [role / identity], [world / genre], [narrative function].
Body lock: [height], [head ratio], [width-height ratio], [leg ratio], [protected silhouette]. All panels show the same physical character asset; do not slim, stretch, beautify, mature, or normalize the body.
Face and hair lock: [face envelope], [eyes], [brows], [nose], [mouth], [skin/texture], [hair/headwear].
Costume lock: [inner layer], [main layer], [outer layer], [waist/belt], [lower body], [footwear], [materials and colors].
Permanent props: [prop geometry], worn on [side], attached by [method], visible in front/side/back, not [common drift].

Layout: wide clean character design board with these modules:
1. large hero bust / 45-degree face close-up;
2. full-body front, side, and back turnaround on the same baseline and scale;
3. height/proportion label panel;
4. expression row with [labels];
5. wardrobe/state variants [list];
6. prop detail close-ups [list];
7. habitual action / skill panels [list];
8. material and color palette strip.

Text: short readable Chinese headings and labels only: [exact labels]. No long biography paragraphs.
Style: [project style], neutral design-board background, clear panel borders, production concept art finish, touchable material details.
Consistency anchors: [anchors].
Avoid: single full-body render, poster layout, scenic background, inconsistent front/back, changed body shape, missing mouth, prop becoming generic, unreadable clutter.
QC: all panels depict the same character, same body proportions, same face, same costume logic, same permanent props, readable section hierarchy.
```

## Common Repair Phrases

If the output becomes a single character render:

```text
Regenerate as a complete multi-panel character design sheet. Keep the existing character, but add labeled modules for front/side/back turnaround, expressions, wardrobe states, prop details, actions/skills, and palette.
```

If front and back differ:

```text
Repair the turnaround only. Front, side, and back must be the same body rotated in place: same head size, body width, leg length, waist height, strap path, prop side, bag side, sleeve length, hem line, hair volume, and foot baseline.
```

If the character is slimmed or stretched:

```text
Restore the original locked body proportions. Do not stretch height or reduce body width. Height labels annotate the existing body and must not alter the silhouette.
```

If a prop drifts:

```text
Repair the permanent prop geometry. It is [exact shape], worn on [side], attached by [cord/strap/clasp], made of [material], visible from front and back; not [wrong objects].
```
