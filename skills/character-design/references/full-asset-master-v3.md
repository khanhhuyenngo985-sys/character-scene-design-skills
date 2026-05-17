# Full Asset Master V3 / 全资产制作门

Use this reference when a request needs a reusable asset library, a script-to-assets breakdown, or coordinated character / scene / prop prompt production. Keep it model-agnostic: the same decisions can later become MJ, Nano Banana, GPT Image 2, Seedance, or another tool-specific prompt.

## Core Rule

Separate assets before writing prompts:

| Asset class | Contains | Must not contain |
| --- | --- | --- |
| Character | one role, body, face, hair, costume, permanent wearable anchors, expression / posture range | full scenes, temporary story props that need their own readable card |
| Scene | location, layout, entrances, actor zones, fixed objects, light, material, atmosphere people when needed | hero character design, detachable prop sheets |
| Prop | one object / mechanism / evidence item, full silhouette, material, state, functional details | people, hands as owners, whole scene backgrounds |

Exceptions:

- A permanent wearable prop belongs in the character anchor, but should also get a prop detail card if its geometry often drifts.
- A fixed spatial prop belongs in the scene anchor.
- A temporary story prop gets its own `PROP_` packet only when it must be read clearly on screen.

## Intake

Before generating any asset, lock these inputs:

| Field | Decision |
| --- | --- |
| Image type | realistic, 2D, 3D, animation, clay, pixel, UI, etc. Do not default to live action when the project is stylized. |
| Genre / era / world | historical, xianxia, fantasy, modern, sci-fi, cyberpunk, post-apocalyptic, wuxia, crime, medical, etc. |
| Global style anchor | camera/render language, color world, material finish, reference limits |
| Asset scope | scene list, character list, key prop list |
| Text policy | Chinese natural language by default; English only for technical labels or model parameters |

## Script Scan To Manifest

When given story text, first return an asset manifest:

```text
SCENE_ list: all named or plot-functional locations, with story task and required atmosphere people.
CHAR_ list: all recurring or plot-functional roles, with identity, body/face needs, costume states, and permanent anchors.
PROP_ list: all readable objects that cause action, prove information, unlock a rule, or must stay consistent.
Global exclusions: what the generation must not import from another era, market, species, body type, or art style.
```

Do not omit a scene, character, or prop that changes the plot.

## Scene Card Gate

Scenes are not empty backgrounds unless the task explicitly asks for an unmanned atmosphere plate. Add atmosphere people when they help the world feel occupied, but keep them subordinate to the main action lane.

Atmosphere people examples:

| Scene type | Atmosphere people |
| --- | --- |
| school / academy | students, teachers, guards, clerks |
| office / institution | staff, clients, security, assistants |
| kitchen / home | family members, servants, cooks, neighbors |
| street / market | pedestrians, vendors, diners, traffic, patrols |
| ancient tavern / inn | servers, drinkers, travelers, stable hands |
| medical / lab | doctors, nurses, patients, technicians |

Use the seven-layer scene prompt order:

1. Worldview positioning: realism level, era, genre, scene type, art direction.
2. Location and geography: where it sits and how one enters or exits.
3. Main structure: form, roof/top system, material aging, signage / ornament, craft standard, base nodes.
4. Extended space: surrounding facilities, thresholds, working surfaces, circulation.
5. Natural / background layers: sky, terrain, vegetation, weather, distance.
6. Light and color: source, direction, contrast, palette, atmosphere.
7. Technical / style spec: lens, render language, material detail, composition, output use.

Scene QC:

- The scene has a clear layout, entrance / exit, and actor activity zone.
- Light, color, and material support the narrative task.
- Atmosphere people match era, identity, and scale, and do not steal focus.
- Fixed anchors can be repeated in later prompts.
- World / era details do not conflict.

## Character Card Gate

A character prompt should lock body, face, hair, costume, and permanent anchors before requesting a dense finished sheet.

Minimum character fields:

| Field | Need |
| --- | --- |
| Identity | name, job / faction, age range, gender or species, era / world |
| Face anchors | face envelope, brows, eyes, nose, mouth, bone structure, skin tone, marks |
| Body anchors | height, head ratio, width-to-height ratio, leg ratio, shoulder / waist logic, posture |
| Hair / headwear | era-correct style, volume, tie, ornament, silhouette |
| Costume layers | inner layer, main layer, outer layer, waist / belt, lower body, footwear |
| State | clean, damaged, ceremonial, workwear, travel, disguise, weathered, etc. |
| Permanent anchors | wearable props, scars, bags, badges, tools that must stay with the character |

Recommended character sheet layout:

1. Main visual area: full-body front, side, and back views.
2. Supplemental area: face close-up and palette.
3. Detail area: accessories, identity markers, material close-ups.
4. Half-body / performance area: upright portrait, expressions, posture or action notes.
5. Background: white, light gray, parchment, or neutral design board, depending on world style.

Character QC:

- Height annotation never stretches, slims, or normalizes the body.
- Front / side / back views look like the same physical asset rotated.
- Wardrobe variants preserve body width, head ratio, leg length, face, hair, and permanent prop ownership.
- Mouth, hands, and small anchors remain visible when they matter.
- Costume and hair match the era / world.

## Prop Card Gate

Use a prop card for anything that must keep shape or mechanism across images or videos.

Minimum prop fields:

| Field | Need |
| --- | --- |
| Name / category | weapon, magic item, tool, token, evidence, vehicle, tech gear, plot object |
| Relation | owner, scene, story function, current state |
| Scale | size, hand relation, body relation, weight impression |
| Form | silhouette, main parts, proportions, front / back logic |
| Material | main material, secondary material, inlay, texture, age marks |
| Details | pattern, inscription, clasp, mouth, hinge, seam, damage, functional surfaces |
| Mechanism | how it opens, leaks, rings, glows, breaks, stores, reads, triggers, or fails |

Default prop composition:

- front view
- back / reverse view
- side view or thickness view
- close-up of the functional detail
- optional scale reference without people, unless a hand-scale guide is explicitly required

Prop QC:

- The full object is readable and not cropped into decoration.
- No people or owner bodies appear in a clean prop card.
- The shape cannot drift into a generic bottle, pouch, ball, badge, weapon, or ornament.
- Material and mechanism match the world.
- Text / symbols are included only when the model can render them reliably or the prompt says they are decorative.

## Material And Color Gate

Every prompt needs touchable material language:

| Material | Useful anchors |
| --- | --- |
| wood | grain direction, cracks, lacquer wear, carved edges, dampness |
| stone | chips, moss, mineral veins, dust, weight, erosion |
| metal | oxidation, scratches, hammered edges, gilding, polished contact zones |
| fabric | weave, fray, folds, seams, stains, embroidery, padding |
| glass / crystal | refraction, thickness, edge highlights, internal bubbles |
| ceramic | glaze, chips, firing marks, painted pattern, worn rim |
| plastic / composite | molded seams, matte / gloss contrast, scuffs, printed marks |
| electronics | ports, indicator lights, screws, heat marks, modular panels |

Use one main color family, one support color, and one accent unless the world style demands otherwise. Avoid arbitrary high-saturation colors that do not come from story, status, faction, or material.

## Output Shape

For full asset production, return:

1. Asset manifest.
2. Global style / era / image-type lock.
3. `SCENE_` cards.
4. `CHAR_` cards.
5. `PROP_` cards.
6. Model-specific prompt packets only after the cards pass QC.
7. Final self-check: separation, material, era/world, proportion, prop geometry, color, and missing assets.
