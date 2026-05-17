---
name: character-design
description: Use when designing, revising, diagnosing, or prompting AI-video or image-generation characters, character sheets, casting assets, character cards, relationship matrices, genre cast packs, wardrobe state ladders, height/proportion locks, turnaround consistency, video-readiness gates, 身高比例锁, 三视图一致性, 成品角色图, 角色关系矩阵, 服装状态卡, 角色一致性, 角色DNA, 表情姿态, 服化道, 道具锚点, or character drift in multi-shot workflows.
---

# Character Design Runtime

This is the lean runtime entry for character design. The full manual remains available as on-demand knowledge, but the default path should produce a usable character packet fast.

Core principle: make the character memorable, stable, and filmable. Do not optimize for prettiness; optimize for difference, silhouette, behavior, identity permission, and repeatable visual anchors. For production-critical roles, treat the character card as a frontloaded asset: the reference image is already part of the prompt. The workflow is model-agnostic; adapt the prompt wording to the user's image or video tool.

When an existing character reference or unusual body shape matters, do not start with a finished character sheet. First lock the base asset: proportion / height, face, permanent props, then W0 turnaround. A full sheet with expressions, wardrobe, skills, and text comes only after those bases pass QC.

For multi-shot or multi-segment AI video, separate immutable identity anchors from mutable character state. The same character should keep silhouette, face/hair, costume category, signature prop, and posture habit, while body state, emotion, fatigue, damage, prop ownership, gaze, and action residue evolve visibly across segments.

For cross-scene or cross-style video work, make a character keyframe or character sheet before video prompting. The sheet should lock identity anchors, expression range, costume, permanent wearable props, and the hand / body surfaces that interact with those props. The video model should animate a solved asset, not invent the role design inside the action prompt.

For audience-facing protagonists, add a likability pass before polishing design. A character becomes easier to follow when the first scene visibly gives at least one of: unfair treatment, kindness toward a specific subject, or distinctive ability / success potential. These must become actions, object relationships, posture, props, or skills, not personality labels.

For specialized live-action or short-drama asset libraries, treat each image as casting + wardrobe fitting + identity proof. Read the short-drama references only when the user explicitly asks for casting libraries, vertical drama roles, or episode-ready short-drama production.

## Output Contract

For most tasks, produce a compact character packet:

| Field | Answer |
| --- | --- |
| Character tag | `@name` |
| Asset stage / 资产阶段 | proportion_lock, face_lock, W0_turnaround, wardrobe_ladder, final_sheet, video_ready |
| Narrative function |  |
| Ensemble contrast / 群像差异 |  |
| Identity buff / 身份增益 |  |
| Specialty / 擅长 |  |
| Permissioned actions / 身份授权动作 |  |
| Toolchain / 专属工具链 |  |
| Visual proof / 能力可见证据 |  |
| Power limit / 能力边界 |  |
| Failure habit / 失败习惯 |  |
| Archetype mix |  |
| Want / Need / Flaw |  |
| Likability levers | unfair treatment, specific kindness, distinctive ability / success potential |
| Silhouette |  |
| Body proportions |  |
| Height / proportion lock | net height, styled max height, head ratio, width-height ratio, leg ratio, baseline rule |
| Face / hair anchor |  |
| Bone structure / 骨相锚点 | cranial shape, face envelope, cheek / jaw, eye structure, nose / lips |
| Skin / texture anchor | age, undertone, pores, finish, marks |
| Neck / hand secondary anchors | collarbone, neck line, hand shape, scars, moles, nails |
| Facial forbidden drift | wrong face shape, wrong eye style, age/makeup/style drift, plastic skin |
| Color anchor |  |
| Costume / material anchor |  |
| Prop anchor |  |
| Permanent prop geometry / 常驻道具几何 | wearing side, shape, attachment, material, front/back visibility |
| Posture signature |  |
| Expression range |  |
| Action signature |  |
| Relationship / blocking role |  |
| Relationship edges / 关系压力线 | power_over, protects, betrays, secret_about, romantic_pressure |
| Genre cast pack slot / 类型包槽位 | lead_entry, primary_desire, shadow_rival, family_power, institutional_gatekeeper, etc. |
| Wardrobe state ladder / 服装状态 | W0 public mask, W1 humiliation workwear, W2 pressure damage, W3 reveal event, W4 intimate recovery, W5 final power |
| Turnaround contract / 三视图契约 | front/side/back must preserve body width, leg length, waist line, straps, prop side, back logic |
| Video readiness / 视频可用性 | video_ready, needs_face_lock, needs_prop_lock, image_only, reroll_priority |
| Consistency anchors |  |
| Current state / 状态连续性 | body state, emotion, fatigue, facing, prop state, residue, next inherited state |
| Forbidden drift |  |
| Frontloaded asset gate |  |

If the user asks for a simple prompt, include a prompt-ready anchor block after the card. If they need a reusable prompt packet or model-specific image prompt, convert the card into the local image-prompt framework used by the project.

## Story Upstream Bridge

Use the installed story skills as diagnosis before visual design when the user provides raw story text, a novel/IP, a loose outline, or asks why a character should look or behave a certain way. They are upstream inputs, not replacements for this skill.

| Upstream need | Use | Convert into |
| --- | --- | --- |
| Story world, ensemble, genre, and relationship map are unclear | `story-five-elements` | narrative function, ensemble contrast, relationship / blocking role |
| A specific role needs a grounded card | `character-profile` | identity buff, Want / Need / Flaw, failure habit, likability levers |
| The character crosses plot turns or multiple segments | `plot-keypoints` | current state, action residue, next inherited state, costume / prop state |
| Visual continuity must survive later shots or segments | project story ledger / continuity notes | protected anchors, prop ownership, state changes, forbidden drift |

Translate story findings into visible anchors:

- Narrative function becomes archetype mix, blocking role, and permissioned actions.
- Identity and occupation become toolchain, material marks, costume logic, and hand habits.
- Want becomes gaze, reach, lean, grip, or path through space.
- Need becomes the body state or prop relationship a scene quietly exposes.
- Flaw becomes a repeated posture, wrong tool use, delayed reaction, or failure habit.
- Relationship pressure becomes height contrast, distance, eyeline, color opposition, and left / center / right blocking.
- Major plot turns become continuity states: damage, residue, fatigue, confidence, shame, prop ownership, or costume change.
- Story facts become character anchors only when they can be seen: body, costume, prop, posture, action permission, or residue.

Do not paste biography into the final prompt. Use biography only to earn visual proof, stable anchors, and filmable behavior.
Do not import short-drama assumptions unless the user explicitly asks for short drama; default to animation, film, concept, ad, or asset-production logic.

## Bone And Face Structure Layer

Use `references/bone-face-structure-layer.md` when close-ups, portraits, character sheets, beauty/fashion frames, live-action style images, or recurring video segments need stronger face consistency. Treat bone structure as an identity anchor, not a universal prettiness recipe.

Lock only the face traits that must survive generation:

- Cranial shape and face envelope: crown height, head-to-face ratio, oval/square/round/long/tapered logic.
- Cheek, jaw, brow, eye, nose, and lips: choose the few structures that make the face recognizable.
- Skin, hairline, neck, and hands: use as secondary anchors when they help identity or performance.
- Facial forbidden drift: name the wrong face shape, eye style, age, makeup, ethnicity/style shift, or plastic-skin problem to avoid.

For groups, vary at least two of face envelope, cheek/jaw logic, eye geometry, hairline, skin texture, or posture so faces do not merge.

## Production Asset Pipeline

Use this when making reusable character assets, GPT Image / MJ / Nano Banana character sheets, or any role with a strong reference image.

```text
CHAR_ASSET_PIPELINE_V1
character DNA -> proportion / height lock -> face and permanent prop lock -> W0 turnaround -> wardrobe states -> final character sheet -> motion audition
```

Do not let a finished sheet invent the base asset. Complex sheet layouts often normalize bodies, average props, and make front / back views inconsistent. Split the work:

1. **Proportion / height lock first.**
   - Height is geometry, not only a label. Record net height, styled max height, head ratio, width-to-height ratio, leg ratio, neck visibility, foot baseline, and relative group height.
   - If the character is nonstandard, exaggerate the protected silhouette in the base prompt. Example for a short round role: `2.8-3.2 heads tall, body width 80-90% of net height, legs 12-18% of height, invisible neck, low center of gravity`.
   - A height ruler must annotate the body, not stretch it. If the ruler makes the model taller, remove the ruler and make a clean proportion base first.

2. **Face and mouth / hand anchors second.**
   - Lock the few features that make the face survive: face envelope, cheeks, eyes, nose, mouth shape, brows, skin marks, hairline.
   - Small mouths, teeth, tusks, whiskers, gloves, wrapped hands, or unusual hands must be named as visible anchors. Do not let texture, beard, fur, or blush cover the mouth.

3. **Permanent prop geometry third.**
   - Permanent wearable props need exact geometry, side, attachment, material, and front / back behavior.
   - Name what the prop is not when common drift is likely. Example: a waist gourd is a double-bulb vessel, small upper bulb, larger lower bulb, pinched waist, short mouth, tied by cord; not a round ball, bell, water bottle, pumpkin, pouch, or jar.

4. **W0 turnaround before full sheets.**
   - Generate only front / side / back in the default outfit before expressions, skills, wardrobe, or text.
   - The views must look like one physical puppet rotated: same body width, head size, leg length, waist height, sleeve length, hem shape, strap path, prop side, bag side, hair mass, and foot baseline.
   - Back view must explain front anchors instead of inventing new ones. If the front has a diagonal strap, gourd on right hip, bag on left hip, or sleeve patch, decide how each appears from the back.

5. **Wardrobe states after the body passes.**
   - Clothing changes must wrap the locked body. They may change layer, material, color accents, armor level, dirt, damage, or ceremonial detail, but not height, head ratio, body width, leg length, face, hair, or permanent prop ownership.

6. **Final character sheet last.**
   - Build the finished sheet from the passed bases. Use minimal readable labels and keep long biographies outside the generated image when text accuracy matters.
   - If a final sheet drifts, return to the failing base gate. Do not patch a full sheet that never passed proportion or turnaround QC.

## Runtime Flow

1. Identify narrative function.
   - Hero, shadow, mentor, trickster, ally, herald, guardian, shapeshifter, or a mix.
   - A role must affect story action, not only personality labels.

2. Add identity buff.
   - Give the character a world-recognized identity, trade, role, rank, oath, craft, disease, curse, tool access, or social permission.
   - Name what they are good at, what actions this lets them perform, and which objects or materials should appear because of it.
   - Make the buff visible: scars, stains, badges, hand habits, tool wear, posture, ritual marks, or carried objects.
   - Keep a limit or failure habit, so the buff creates drama instead of solving everything.

2A. Add likability levers for protagonist or audience-entry characters.
   - Unfair treatment: show what is taken, denied, misunderstood, trapped, cursed, or forced on them.
   - Specific kindness: name who or what they protect, repair, spare, retrieve, remember, or care for.
   - Distinctive ability / success potential: show a visible skill, body trait, beauty, courage, comic habit, tool access, or specialty that suggests they may win.
   - Turn each lever into visual proof: a held object, a repeated hand habit, a protective blocking choice, a skill demonstration, a body consequence, or a prop relationship.

3. For new or production-critical characters, run the frontloaded asset gate.
   - Design the cast or subject-library board before polishing a single person.
   - Mix archetypes/functions, then convert them into posture, color, costume, prop, and identity-buff anchors.
   - For existing references or unusual silhouettes, create a proportion / height lock before any final sheet.
   - Pass W0 front / side / back consistency before adding wardrobe variants, expression rows, skill panels, or dense text.
   - For live-action casting libraries, also check gender/age/ethnicity distribution, lead attractiveness tier, bone/face-structure contrast, and whether each role has a visible social or institutional power lever.
   - For recurring wearable props, include callouts or multi-view details before video: wearing side, reveal pose, button / clasp / mouth surface, and failure mode.
   - Create posture states, not only a standing reference: default, pressure, relationship, action, failure, and arc.
   - Test a still asset with a short motion audition before trusting it in multi-reference video.
   - For the detailed method, read `references/frontloaded-character-assets.md`.

4. Build difference.
   - Contrast body, hair, color, costume, material, posture, and prop against nearby characters.
   - For groups, design the cast as a visual system before polishing individuals.

5. Lock three anchor layers.
   - Immutable anchors: silhouette, body ratio, face / hair / bone structure, signature prop.
   - Variable performance: expression, pose, costume state, action intensity.
   - Forbidden drift: age, species, costume category, color swap, prop loss, style mismatch.

6. Translate psychology and buff into posture and action.
   - Want becomes gaze, reach, lean, direction, or grip.
   - Flaw becomes repeated body habit or wrong solution.
   - Need becomes what the scene quietly exposes through action.
   - Specialty becomes tool use, gesture vocabulary, stance, material handling, or scene access.

7. Plan blocking if multiple characters appear.
   - Separate by height, color, left/center/right, distance, eyeline, and movement rhythm.
   - Do not let two characters share the same silhouette, palette, and posture role.

7A. For serialized, ensemble, or episode-based production, convert the cast into a playable system.
   - Build a relationship matrix: power_over, protects, betrays, secret_about, romantic_pressure, and scene_trigger.
   - Build a genre or world cast pack: 8-12 role slots that satisfy the project promise before choosing extra faces.
   - Build a wardrobe state ladder for recurring roles: public mask, work state, pressure damage, reveal event, recovery, final state.
   - Run a video readiness gate for core assets before multi-scene or multi-episode production.
   - For short-drama specialization, read `references/shortdrama-character-production-system.md`.

8. Handoff to AI video.
   - Reduce the design to 3-5 stable prompt anchors.
   - Include 1-2 identity-buff anchors when they unlock needed action or props.
   - In multi-reference video prompts, bind the buff directly after the character handle: `@Character = identity buff + specialty + toolchain + permissioned actions`.
   - Name what must not change.
   - Name what has changed in this segment's character state.
   - Keep movement constraints clear enough that the model can preserve identity.

## Character State Ledger

Use this when one character crosses multiple shots or 15-second segments.

| Field | Purpose |
| --- | --- |
| Identity anchors | what stays the same: silhouette, body ratio, face/hair, costume category, signature prop |
| Previous final state | posture, facing, location, hand/foot/gaze, prop ownership, body deformation |
| Current emotional pressure | proud, ashamed, exhausted, curious, hiding, overconfident, relaxed |
| Body state | round, flattened, stretched, dusty, wet, stuck, falling, seated, limping |
| Costume / prop state | sleeve, belt, gourd, hat, robe, tool visibility and damage |
| Action residue | ink, dust, snow, scorch, sweat, wobble, ringing, breath |
| Allowed change | what may evolve in this segment |
| Protected anchors | 3-5 identity details that cannot drift |
| Next inherited state | what the next segment must see in the first 2 seconds |

Character continuity is not keeping the character clean. It is preserving identity while carrying visible consequence.

## Identity Buff Layer

Use this layer when a plain character description cannot produce the needed action, object, or authority. The buff is not biography filler; it is a production lever.

| Buff field | Purpose |
| --- | --- |
| Identity buff | Who the world recognizes this character as. |
| Specialty | What the character can naturally do on screen. |
| Permissioned actions | Actions that become believable because of the identity. |
| Toolchain | Objects, materials, marks, or instruments that should appear. |
| Visual proof | The visible evidence that the buff is real. |
| Power limit | What the buff cannot solve. |
| Failure habit | How the character fails in body, not explanation. |

Weak:

```text
a young Taoist priest
```

Stronger:

```text
a young Taoist priest who repairs city-protection talisman arrays, skilled with cinnabar thread, cracked bronze bells, and torn yellow talismans; three damaged talismans held between the left fingers, cinnabar burn marks on the right fingertips, always looking first at cracks in the ground-veins
```

For Western live-action drama, prefer institution-specific buffs over generic wealth/status. Examples: trustee signature authority, probate executor certification, district attorney subpoena power, insurance pre-authorization denial, hospital board vote, private-school admissions list, HOA fine notice, zoning variance vote, charity grant access. Make the power lever visible through folder, badge, stamp, binder, map tube, clipboard, envelope, or posture.

## DNA Checklist

Use the seven-part character DNA, but keep it concise:

- Group contrast: who this character differs from.
- Archetype mix: two functions in tension.
- Identity buff: what world role, skill, tool access, or permission lets the character do more than an ordinary person.
- Posture: spine, center of gravity, limb openness.
- Expression: default face and extreme face.
- Color: high-recognition color or palette contrast.
- Costume / prop: story-bearing visual anchor.
- Extreme contrast: the one detail that makes the character hard to forget.

## Consistency Rules

Every shot or prompt should preserve:

- Body shape and height relationship.
- Numeric proportion lock when present: net height, styled max height, head ratio, width-height ratio, leg ratio, baseline.
- Face / hair marker.
- Main color block.
- Costume material or accessory.
- Signature prop.
- Posture or movement habit.

When consistency breaks, fix anchors before adding more style words.

For character sheets and turnarounds, also verify:

- Front, side, and back are the same body rotated, not three similar redesigns.
- Feet share one baseline; head, waist, hem, knee, and prop heights line up.
- Straps, belts, patches, bags, scabbards, gourds, tails, wings, horns, backpacks, or robes continue logically across views.
- Wardrobe variants keep the locked body and permanent props; clothing changes do not create a taller, slimmer, younger, or more heroic version.

Every multi-segment prompt should also carry:

- Body state and facing direction.
- Gaze or attention direction.
- Hand/foot position when it drives the next action.
- Costume and prop state.
- Fatigue, shame, pride, confidence, or relaxation as visible posture.
- Deformation, residue, or impact marks that the next segment must inherit.

## Permanent Wearable Prop Anchors

Some props are not temporary story objects; they are part of the character's identity and continuity. Examples: a left-wrist smart watch, belt gourd, bracelet, ring, badge, talisman pouch, or weapon scabbard.

For these, record:

| Field | Purpose |
| --- | --- |
| Wearing side / location | left wrist, right hip, belt front, back strap |
| Visibility rule | when sleeve, robe, hand, or pose should reveal it |
| Interaction surface | button, crown, clasp, mouth, string, bell, screen |
| Failure mode | too small to press, slips under sleeve, swings late, catches on cloth |
| Continuity state | intact, cracked, glowing, ringing, loose, stained |
| Geometry guard | exact shape and common wrong substitutes to avoid |

Wearable props should be included in the character anchor block and repeated in video prompts when they drive action. They should not be promoted to an independent `@Prop` unless the scene treats them as a separate object detached from the body.

If the prop is visually easy to average into a generic object, define its silhouette. For example, a waist gourd is a double-bulb vessel with a small upper bulb, larger lower bulb, pinched waist, short neck, cord tied around the neck, and natural gourd / clay-brown material; it is not a sphere, bell, pouch, jar, canteen, pumpkin, or water bottle.

## Style-Specific Character Sheets

When adapting a referenced character into a strong graphic style, preserve identity anchors while replacing rendering rules.

For old black-and-white manga / 80s-90s manga:

- Preserve: face/body from reference, hair silhouette, eye shape, brows, costume category, permanent prop.
- Style lock: heavy black ink, bold nib outlines, cross-hatching, screentone dots, aged paper, high-contrast black and white.
- Value lock: no color and no gray wash; use pure black, pure white, line density, and screentone.
- Costume lock: black suit as readable black mass, white shirt as clean white area, folds shown with cross-hatching.
- Prop lock: left-wrist smart watch remains on the left wrist in every applicable view.

This style is useful when the design needs strong graphic memory and clear identity anchors before video generation.

## Prompt Anchor Block

Use this when handing to image or video models:

```text
[@CharacterTag], [identity buff], [specialty/toolchain], [body shape + proportion lock when needed], [face/hair anchor], [main color/costume/material], [signature prop geometry], [posture/action signature].
Keep consistent: [3-5 anchors].
Avoid: [forbidden drift].
```

For multi-reference video prompts, define the character before the action:

```text
@CharacterTag = [identity buff], skilled at [specialty], uses [toolchain], can perform [permissioned actions], visible proof: [visual proof], keep consistent: [3-5 anchors].
```

Example:

```text
@young-taoist = repairs city-protection talisman arrays, skilled with cinnabar thread and cracked bronze bells, can stitch broken ward-lines in midair, left fingers hold three damaged talismans, right fingertips have cinnabar burn marks, keep consistent: thin body, ash-blue robe, torn yellow talismans, bronze bell belt.
```

For multi-character shots, write each character as a separate block, then describe left/center/right blocking.

## Common Failure Checks

- Is the character only attractive, not memorable?
- Was the character designed alone before seeing the ensemble?
- Could two characters merge if the model saw them together?
- Did the sheet start before the proportion / height lock passed?
- Did a height ruler stretch, slim, or standardize the character's body?
- Do front / side / back look like the same physical asset rotated?
- Do wardrobe variants preserve the same body width, head ratio, leg length, waist line, face, hair, and permanent props?
- Does the design rely on tiny details that vanish in video?
- Is the prop decorative instead of action-bearing?
- Is the permanent prop geometrically identifiable, or did it drift into a generic ball, pouch, bottle, badge, or ornament?
- Do color, costume, and prop leave a memory trace or carry an arc?
- Has the static card passed a motion audition?
- Does the identity buff unlock visible actions, objects, or authority?
- Is the buff proven by costume, tool wear, hand habit, scar, mark, or posture?
- Does the buff have a limit or failure habit?
- Does the pose show intention, or just style?
- Does the current segment inherit the previous body state before changing it?
- Are emotion words translated into face, posture, and body direction?
- Is the forbidden drift list explicit?
- For live-action casting assets: is the full body visible with shoes and floor?
- For culturally specific or live-action casting roles: did face, age, ethnicity, styling, or actor type drift into an unrelated market default?
- Are bone/face anchors specific enough to preserve identity without turning into a generic beauty face?
- Does the image look like a believable actor fitting, not a fashion editorial or concept-art character?
- For power roles: is the legal/social lever visible and specific, or just "rich / powerful"?
- For episodic or ensemble production: do relationship edges create scene triggers rather than static biography?
- Does the genre cast pack cover the required slots before adding decorative characters?
- Do recurring roles have wardrobe states that show story arc without losing identity?
- Has the asset passed a motion audition before being labeled video-ready?

## Deep References

Read only when needed:

| Need | Reference |
| --- | --- |
| Full original runtime manual | `references/full-manual.md` |
| Frontloaded character assets / 重在前期角色资产 | `references/frontloaded-character-assets.md` |
| Optional live-action / short-drama casting assets | `references/live-action-shortdrama-casting-assets.md` |
| Optional short-drama production character system | `references/shortdrama-character-production-system.md` |
| Bone and face structure / 骨相、脸型、五官、防脸漂移 | `references/bone-face-structure-layer.md` |
| DNA details | `SECTIONS/01_角色DNA七字诀详解.md` |
| Consistency and AI drift | `SECTIONS/02_角色一致性维护.md` |
| Relationship blocking | `SECTIONS/03_角色关系设计Blocking.md` |
| Expression and posture | `SECTIONS/04_表情系统与姿态设计.md` |
| Negative design checklist | `SECTIONS/05_负面设计清单.md` |
| Prompt templates | `SECTIONS/06_AI提示词模板.md` |
| Chinese / ink / traditional design | `SECTIONS/07_中国传统角色设计.md` |
| Archetype library | `SECTIONS/08_人物原型库.md` |
| Complete long-form process | `SECTIONS/09_完整设计流程.md` |
| Reference-image philosophy | `SECTIONS/10_参考图哲学与IP宇宙.md` |
| Ensemble design | `SECTIONS/11_群像设计专题.md` |

## Workflow Handoff

When this skill is part of a larger production workflow, return the compact character packet, prompt anchors, asset-stage gates, and QC notes. Let the story or video workflow decide scene structure, shot timing, and model segmentation; let the local prompt framework turn anchors into stable `CHAR_` or `SHOT_` prompt packets when needed.
