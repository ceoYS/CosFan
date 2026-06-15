# CosFan — Pixel Capture Required (read before Claude Design)

**Status: NOT READY for Claude Design as visual input.** Date: 2026-06-15.

This pack is a **UX/IA pattern pack**, not a pixel pack. The written briefs are useful, but
Claude Design needs actual visuals — and right now there are none. This file states exactly
what is missing and how to fix it.

---

## The hard facts

- **Local image count is 0.** No `.png/.jpg/.jpeg/.webp/.gif` exists anywhere under
  `references/mobbin/` (`visual/` holds only a `.gitkeep`).
- **The Mobbin MCP did not produce saved screenshots.** `mcp__mobbin__search_screens` /
  `search_flows` return **inline preview images for on-screen viewing only**, plus a
  `mobbin_url` and a proprietary `https://mobbin.com/api/mcp/short/…` link. There is **no
  file path, no export-to-file resource, no download** — the agent can *view* a screen but
  cannot *save* one. (Persisting the `api/mcp/short` asset would copy Mobbin's proprietary
  screenshot, which the CosFan guardrails, the mining skill, and the operating rules forbid.)
- **Existing Mobbin URLs are not reliable design input.** The `mobbin_url` / `api/mcp/short`
  links are **provenance only**. They were tested and **do not reliably open outside the
  authenticated Mobbin MCP/session**, so they **cannot be handed to Claude Design** and are
  **not sufficient as Claude Design visual input**.

> Net: the manifest's per-reference briefs tell Claude Design *what pattern to learn*, but
> there is **no image** for it to look at. That gap must be closed before Claude Design.

---

## What we need before Claude Design (pick one)

**A. Manual screenshots saved locally** — the user opens each reference in a licensed Mobbin
session and uses the OS screenshot tool, saving the files into
`references/mobbin/curated/CLAUDE_DESIGN_INPUT_PACK/visual-local/`. Local-only, never committed.

**B. A Claude Code-generated visual board from inline MCP inspection** — Claude Code inspects
the screens inline via the Mobbin MCP and then **generates its own original visual board**
(e.g. an HTML/SVG schematic redrawn in CosFan's "Cool Pastel Collectible OS" language). This is
a synthesized artifact, **not** a copy of Mobbin's pixels, so it is safe to save and commit.

Either A or B produces a real visual layer Claude Design can consume. Source pointers alone
do not.

---

## Recommended path

**Manual screenshots for the 12–16 core references.** It is the fastest, highest-fidelity, and
lowest-risk option (B requires Claude Code to redraw every screen and only ever approximates).
The prioritized capture list — target filename, source app, pattern to search, why, what to
learn, what not to copy — is in **`MANUAL_SCREENSHOT_QUEUE.md`**.

1. Capture the 12 core targets in `MANUAL_SCREENSHOT_QUEUE.md` (stretch to 16 if useful).
2. Save them into `visual-local/` with the queue's target filenames.
3. Update each `VISUAL_REFERENCE_MANIFEST.md` row: set `local_visual_path` and flip
   `manual_capture_needed` to `no`.
4. Re-run the readiness check in `VISUAL_EVIDENCE_AUDIT.md` — once the core groups have local
   images, the verdict flips from NOT READY to READY.

---

## Folder + git hygiene

- Local captures go in `visual-local/` (this folder is created alongside this file).
- **Recommendation:** add `visual-local/` to `.gitignore` so proprietary captures are never
  committed. *(Not applied here — `.gitignore` is only edited on explicit request.)* Suggested
  lines:
  ```
  references/mobbin/curated/CLAUDE_DESIGN_INPUT_PACK/visual-local/*
  !references/mobbin/curated/CLAUDE_DESIGN_INPUT_PACK/visual-local/.gitkeep
  ```
- Do **not** commit or create extracted Mobbin proprietary images. Manual captures are
  local-only. A Claude-generated original board (option B) is the only image artifact that may
  be committed.
