# Mobbin Reference Collection — STATUS

**Status:** ✅ COMPLETE — Mobbin Reference Collection v0
**Date:** 2026-06-15
**Mobbin MCP:** authenticated (`✔ Connected`) and used (iOS, `search_screens` + `search_flows`).

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
