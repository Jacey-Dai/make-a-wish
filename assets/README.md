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
