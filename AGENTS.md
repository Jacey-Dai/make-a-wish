# AGENTS.md

Instructions for any coding agent (Claude, Cursor, Codex, Copilot, …) working on this repo.

## What this is

许愿池 (wishing pond): a single-page canvas toy. Touch the water to make ripples and scare the koi; hold and flick upward to toss a coin; land it in the stone bowl at the center to write a wish that floats away as a lantern.

- Requirements, task board and changelog: [`docs/PRD.md`](docs/PRD.md). This file is the source of truth for agents.
- Code: [`index.html`](index.html). One file, no build, no dependencies. Open it in a browser to run it.

## Before you start

1. Read `docs/PRD.md` in full, including the last 3 changelog rows.
2. Pull the latest `main`.
3. Pick **one** feature whose status is `待认领` and whose dependencies are `已完成`. Do not touch a feature someone else has claimed.
4. Claim it in your PR (set status `进行中` and owner `name / platform` in the PRD feature table).

## While you work

- Branch name: `feat/F<id>-<short-english-name>`, e.g. `feat/F3-falling-leaves`.
- Put new code in its own commented section, tagged with the feature ID: `/* ---------- F3 leaves ---------- */`.
- Follow the "技术约定" section of the PRD: CSS-pixel coordinates, the pond ellipse `pond {cx, cy, rx, ry}`, scale everything by `S`, use `inWater()`/`clampWater()`, Pointer Events only, `store.get/set` for localStorage (keys are prefixed `wishpond.`). There is no audio right now; do not add sound outside F6.
- Follow the "美术方向" section of the PRD (sunlit mossy ruins, clear emerald water with lily pads and small white flowers, see-through ripples, 3/4 view). New visuals must use its palette and lighting.
- Game logic uses world coordinates; the water layer is squashed by `view.T`. Use `toScreen()` / `toWorldY()` when drawing on the screen layer. Pointer positions from `pos()` are already in world coordinates.
- Keep the per-frame draw order in `frame()` intact; decide which layer your object belongs to (water layer or screen layer).
- UI text in Chinese, code and comments in English.
- If you must change shared code (`layout`, `frame`, input handlers), say so in the PR.

## Done means

- Every acceptance item for the feature in the PRD is checked, or explicitly listed as skipped with a reason.
- Tested at ~1280px desktop and ~390px phone width (touch emulation), no console errors, no horizontal scroll.
- PRD updated in the same PR: feature status `待验收`, acceptance boxes ticked, one new changelog row at the top, version comment at the top of `index.html` bumped.
- PR description contains the handoff note: what was done, what was skipped and why, shared code touched, new localStorage keys, gotchas for the next agent.

Jacey plays the build and merges; the feature becomes `已完成` then.
