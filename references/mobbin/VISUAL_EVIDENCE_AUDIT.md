# CosFan — Visual Evidence Audit

**Date:** 2026-06-15
**Scope:** curated Claude Design Input Pack only (`curated/CLAUDE_DESIGN_INPUT_PACK/`).
**Question:** does the reference collection have legitimate visual evidence (saved images)
for the curated pack, or only markdown notes?

---

## 1. Mobbin MCP capability check (verified live, not assumed)

| Probe | Result |
|---|---|
| `claude mcp list` | `mobbin … ✔ Connected` (authenticated) |
| `ListMcpResourcesTool(mobbin)` | only 2 resources, both `ui://mobbin/search-{screens,flows}.html`, mime `text/html;profile=mcp-app` — **inline galleries, no export** |
| `mcp__mobbin__search_screens` (live) | returned inline images + JSON: `mobbin_url` + proprietary `https://mobbin.com/api/mcp/short/…` image link. **No file path, no export artifact.** |
| `mcp__mobbin__search_flows` (live) | same shape; returned live Patreon flow `fdde05b8-…` = curated ref 7 → **source pointers resolve** |

**Did Mobbin MCP provide screenshot/image EXPORT resources? → NO.**
It provides inline preview images **for on-screen viewing only** plus canonical `mobbin_url`
links to cite. There is no screenshot/image export-to-file capability. Saving the
`api/mcp/short` asset to disk would mean copying Mobbin's proprietary screenshots —
forbidden by the CosFan guardrails, the mining skill ("never save/commit screenshots"), and
the operating rules ("do not copy competitor UI/assets"). We were authenticated and could
view every screen; we deliberately did not extract assets. Playwright bypass and scraping
were not used (explicitly out of bounds).

---

## 2. Image count

| | Count |
|---|---|
| Image files before (`references/mobbin`, png/jpg/jpeg/webp/gif) | **0** |
| Image files after | **0** |
| Visual files saved this sprint | **0** |

This is **by policy + capability**, not an omission. The pack is a **UX/IA pattern pack,
not a pixel pack.**

### Visual files saved
- None. (`visual/` contains only `.gitkeep`.)

### Curated references WITH a saved visual (file)
- None (0 / 26).

### Curated references WITH a source pointer (provenance only — NOT design input)
- All 26 / 26 — every row in `VISUAL_REFERENCE_MANIFEST.md` carries a `mobbin_url`
  `source_pointer` + a written visual-inspection brief. **Provenance only:** these URLs
  record where each pattern was found; they are **not guaranteed to open outside the
  authenticated Mobbin MCP/session** (the user verified they do not reliably open) and are
  **not sufficient as Claude Design visual input**.

### Curated references WITHOUT any visual evidence at all (no file, no pointer)
- None.

---

## 3. Minimum required visual-coverage checklist

Gate = does each core screen group have **usable Claude Design visual input** before Claude
Design? `source pointer` = a Mobbin URL recorded as **provenance only** (not guaranteed to open
outside the authenticated Mobbin MCP/session, not sufficient as visual input). `file` = a saved
local screenshot **or** an MCP-derived visual board — the only artifacts that count as input.

| # | Core screen group | Curated refs | Source pointer | Saved file | Status |
|---|---|---|---|---|---|
| 1 | Creator profile / membership entry | 7, 9 | ✅ | ❌ | pointer-only |
| 2 | Tier / paywall / plan selection | 8, 10 | ✅ | ❌ | pointer-only |
| 3 | Active subscription / manage membership | 12 | ✅ | ❌ | pointer-only |
| 4 | Block / report confirmation | 23, 24 | ✅ | ❌ | pointer-only |
| 5 | Photocard collection / detail | 17, 18, 19 | ✅ | ❌ | pointer-only |
| 6 | Event notice detail | 20, 21, 22 | ✅ | ❌ | pointer-only |
| 7 | Home / explore or onboarding | 1–6 | ✅ | ❌ | pointer-only |
| 8 | Message channel | 15, 16 | ✅ | ❌ | pointer-only |

**All 8 core groups: provenance recorded, but ZERO usable Claude Design visual input**
(no saved local screenshot, no MCP-derived visual board). Source pointers do not satisfy the gate.

---

## 4. Readiness verdict

> ### NOT READY for Claude Design
>
> Per the corrected rubric: **READY** = usable visual input (saved local screenshots, or an
> MCP-derived visual board) exists for the core 7–8 groups; **NOT READY** = those groups have
> only source pointers / written briefs and no saved visual artifact.
>
> CosFan has **source pointers + written visual-inspection briefs for all 8 core groups**
> (and all 26 refs), but **zero saved image files and no MCP-derived visual board**. Source
> pointers are **provenance only** — **not guaranteed to open outside the authenticated Mobbin
> MCP/session** and **not sufficient as Claude Design visual input**. That is **NOT READY**.

**Correction (supersedes the earlier "PARTIAL is the intended steady state" framing):** the
earlier audit treated pointer-only evidence as sufficient for a pattern/IA pack and called the
pack "Claude-Design-ready at the pattern level." That was wrong about the URLs — the user tested
the Mobbin source pointers and they do **not** reliably open, so they cannot be handed to Claude
Design as visual input. The written IA/pattern briefs remain valuable, but **manual screenshot
capture or an MCP-derived visual board is required before Claude Design.** See
`curated/CLAUDE_DESIGN_INPUT_PACK/PIXEL_CAPTURE_REQUIRED.md` and `MANUAL_SCREENSHOT_QUEUE.md`.
The "re-skin, never reproduce" point still holds — every reference is off-palette at source.

---

## 5. Git hygiene

| Check | Result |
|---|---|
| `visual/` file count | 1 (`.gitkeep` only) |
| `visual/` size | ~0 (text placeholder) |
| Proprietary screenshots present | none |

- **Markdown + manifest + this audit:** safe to commit (no proprietary assets, all original
  notes + outward links).
- **`visual/` folder:** keep as an empty placeholder. If screenshots are ever added manually,
  they should be **local-only**.
- **Proposed `.gitignore`** (NOT applied — propose only; edit on explicit request):
  ```
  references/mobbin/curated/CLAUDE_DESIGN_INPUT_PACK/visual/*
  !references/mobbin/curated/CLAUDE_DESIGN_INPUT_PACK/visual/.gitkeep
  ```
  This pre-empts any future accidental commit of proprietary captures while keeping the
  folder tracked.

---

## 6. Recommendation

- **Safe to commit:** `VISUAL_REFERENCE_MANIFEST.md` (updated), `VISUAL_EVIDENCE_AUDIT.md`
  (this file), `PIXEL_CAPTURE_REQUIRED.md`, `MANUAL_SCREENSHOT_QUEUE.md`, `visual/.gitkeep`,
  and the rest of the markdown collection.
- **Keep local-only:** any manually-captured Mobbin screenshots (none exist yet) — put them in
  `curated/CLAUDE_DESIGN_INPUT_PACK/visual-local/` (recommend git-ignoring it; see
  `PIXEL_CAPTURE_REQUIRED.md`).
- **Do not commit / do not create:** extracted Mobbin proprietary images.
- **Next step (corrected):** the pack is **NOT** Claude-Design-ready as visual input. Source
  pointers are **provenance only** and are **not sufficient as Claude Design visual input**.
  Before Claude Design, produce **either** manual screenshots (`MANUAL_SCREENSHOT_QUEUE.md`,
  12–16 core references) **or** a Claude Code-generated visual board from inline MCP inspection.
