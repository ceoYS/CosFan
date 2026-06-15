# Mobbin Reference Collection — STATUS

**Status:** ✅ COMPLETE — Mobbin Reference Collection v0
**Date:** 2026-06-15
**Mobbin MCP:** authenticated (`✔ Connected`) and used (iOS, `search_screens` + `search_flows`).

> **⚠️ CORRECTION (2026-06-15):** "design-ready" below refers to **UX/IA pattern** readiness only.
> The Mobbin **source pointers are provenance only** — they do not reliably open outside the
> authenticated Mobbin MCP/session and are **not sufficient as Claude Design visual input**. The
> pack is **NOT READY for Claude Design** until manual screenshots or a Claude-generated visual
> board exists. See `curated/CLAUDE_DESIGN_INPUT_PACK/PIXEL_CAPTURE_REQUIRED.md` +
> `MANUAL_SCREENSHOT_QUEUE.md`.

## Delivered
- `MOBBIN_REFERENCE_INDEX.md` — 60 benchmark notes across 11 CosFan screen groups.
- `raw/<group>/*.md` — 60 pattern benchmark notes (text + Mobbin URL pointers only).
- `curated/CLAUDE_DESIGN_INPUT_PACK/README.md` — 24 selected references, design-ready.

## Method
Fan-out: 10 collector subagents (2 waves of 5), one per group, each examined Mobbin
inline images on iOS, wrote benchmark notes, returned a structured summary. Main thread
synthesized the index + curated pack.

## Boundaries held
- No screenshots saved or committed (notes + URL pointers only).
- Discarded all NFT/crypto, voice/video/live-call, dating-swipe, adult/PPV, and
  trading-marketplace references during collection.
- No API keys/tokens stored. No PRD/Spec Kit changes. No app code. Not committed.
