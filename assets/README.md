# Forest sanctuary environment

Generated with the built-in image_gen tool for F9, 2026-10-31.

Prompt: Semi-realistic painterly adventure-game forest sanctuary inspired by Zelda environmental atmosphere, with irregular mossy trunks and roots, layered fern banks, ivy ruins, distant sunlit passage, pale mist, warm upper-left light, shadowed foreground edges, and a quiet empty moss clearing in the lower half. No painted water, pond, UI, text, characters, or copied game landmarks. Natural material detail with painterly simplification, atmospheric perspective; avoid flat geometry, repetitive trees and photorealism.

The plate is static and loaded once. Existing Canvas/WebGL pond and interaction code remains separate. If loading fails, procedural scenery remains available. This adds one local image asset to the previously single-file project.

## v0.12 approved design assets

User approved the scene, deer, shoreline and botanical concepts before implementation. Built-in image_gen produced:

- `forest-sanctuary-v2.png`: approved softer painterly forest concept converted to a background plate; remove the painted pond, wishing bowl, plants, lamp and waterfall water so the live scene can overlay it.
- `botanical-atlas-v1.png`: transparent lily pad and flower atlas matching the approved botanical concept; three pads and open/half-open/bud flower variants, simplified painted shading and natural jade/olive/cream colors.
- `deer-atlas-v1.png`: transparent side-facing deer with standing, two walking strides and grazing poses, matching the approved muted tawny deer study.

Atlas source rectangles are specified in `index.html`; all assets load locally with no external service calls. Existing procedural botanicals remain a load-failure fallback. A deer is hidden until its atlas is ready. Shoreline slabs are rendered procedurally with varied weathered facets, patchy moss and sparse vegetation based on the approved shore concept. The live water shader, wave simulation and wish/coin/lantern logic were preserved.

## v0.13 shore material

`shore-stones-v1.png` generated with built-in image_gen using approved shore concept: three isolated weathered mossy slabs on transparent alpha, soft hand-painted olive gray stone, broad lit faces, patchy moss, stable contact surfaces, no smooth balls or hard low-poly triangles. Source rectangles in index.html; used for static shoreline and waterfall bank caches.

## v0.14 cascade

`rock-cascade-v1.png` generated using built-in image_gen and the user-referenced layout study. Prompt: isolated low mossy rock ledge, visible shallow winding stream feeding an irregular short cascade, soft painted olive/gray material, coherent origin and foamy landing, true transparency, no forest or broad pond patch. Animated highlights are clipped to the water region; the existing wave system receives subtle landing ripples.

## v0.15 pond bed

`pond-bed-v1.png`, built-in image_gen. Prompt: top-down painterly pond-bed material, warm sage sand/silt, small irregular warm-gray and olive stones clustered toward edges, quiet center for readable fish, sparse aquatic tufts and muted fallen leaves. No water, reflections, caustics, fish or UI. Refracted and shaded by the live shader; also used in 2D fallback.
