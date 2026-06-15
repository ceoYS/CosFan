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

### Curated references WITH a source pointer (view-only evidence)
- All 26 / 26 — every row in `VISUAL_REFERENCE_MANIFEST.md` has a live `mobbin_url`
  `source_pointer` + a written visual-inspection brief.

### Curated references WITHOUT any visual evidence at all (no file, no pointer)
- None.

---

## 3. Minimum required visual-coverage checklist

Gate = does each core screen group have visual evidence available before Claude Design?
`source pointer` = live Mobbin URL + inspection brief (viewable). `file` = saved screenshot.

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

**All 8 core groups: source pointer PASS, saved-file FAIL.**

---

## 4. Readiness verdict

> ### PARTIAL
>
> Per the rubric: **READY** = saved visual evidence exists for the core 7–8 groups;
> **PARTIAL** = source pointers exist but image files are missing; **NOT READY** = core
> groups missing both.
>
> CosFan has **source pointers + written visual-inspection briefs for all 8 core groups**
> (and all 26 refs), but **zero saved image files**. That is exactly **PARTIAL**.

**Important nuance:** PARTIAL here is the *intended steady state*, not a blocker. The visual
layer ("Cool Pastel Collectible OS") is CosFan's design-from-scratch differentiation — every
reference is off-palette at source and must be re-skinned, never reproduced. For a
**pattern/IA** pack (which is what Claude Design needs), pointer-only evidence is sufficient;
see `AUDIT.md` ("Claude-Design-READY, conditional"). The screenshot gap only matters if
someone specifically wants a *pixel* reference pack — and that path is documented (manual,
licensed, local-only) in the manifest.

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
  (this file), `visual/.gitkeep`, and the rest of the markdown collection.
- **Keep local-only:** any manually-captured Mobbin screenshots (none exist yet).
- **Do not commit / do not create:** extracted Mobbin proprietary images.
- **Next step:** treat the pack as Claude-Design-ready at the **pattern** level. Only pursue
  manual screenshot capture (manifest §"How to manually capture") if a stakeholder explicitly
  requires a pixel pack.
