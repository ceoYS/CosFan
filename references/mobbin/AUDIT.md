# CosFan — Mobbin Reference Collection AUDIT

**Audited:** 2026-06-15 · against `MOBBIN_REFERENCE_INDEX.md` (60 notes) + `curated/CLAUDE_DESIGN_INPUT_PACK/README.md`.
**Auditor scope:** reference/research documentation only. No app design, no PRD/Spec Kit/code/build changes. Not committed.

## TL;DR

- **Usable for UX pattern mining:** YES — strong. 60 notes, 11 groups, every note carries a full benchmark schema (MVP action + risk notes + canonical Mobbin URL).
- **Collection is markdown-only:** YES. **Zero** image files (`*.png/jpg/jpeg/webp/gif`). 464 KB total. This is the *intended* state (policy: no screenshots saved/committed), not a failure → classify as **UX/IA pattern pack, not a full visual/pixel design pack**.
- **Mobbin MCP screenshot export:** NOT available. `search_screens`/`search_flows` return inline images for *viewing* only; the only MCP resources are two `text/html;profile=mcp-app` galleries. No file/screenshot export. Saving the inline images = copying proprietary Mobbin assets → forbidden by guardrails. → Visual gap is filled by `VISUAL_REFERENCE_MANIFEST.md` (URL pointers), not saved images.
- **Claude Design readiness:** **READY (conditional).** All 7 required screens (§5) have **source pointers**, which the readiness gate accepts in lieu of screenshots. Caveat: the pastel/collectible *visual expression* has no Mobbin precedent by design and must be designed from first principles.
- **One weakness fixed:** curated pack under-represented **Lookbook / Content (0 vs recommended 2)**. Added 2 refs → pack now **26**.
- **Commit:** safe to commit the markdown set when asked; nothing to gitignore (no images exist). Not committing now.

---

## 1. Preflight results

| Check | Result |
|---|---|
| `pwd` | `/mnt/d/Projects/Cos-Fan` |
| Branch | `main` (up to date with `origin/main`); all `references/mobbin/**` + `docs/skills/` are **untracked**, nothing staged |
| `git log` | 2 commits (`360ad1d` PRD/data model, `2194d6b` init). No reference commit yet. |
| Mobbin MCP | `mobbin: https://api.mobbin.com/mcp — ✔ Connected` |
| Total files in `references/mobbin` | 63 (60 notes + INDEX + STATUS + curated README) + 3 `.gitkeep` |
| Markdown files | 63 |
| **Image files** | **0** (png/jpg/jpeg/webp/gif) |
| Size | 464 KB |
| Source pointers | 60 notes → 60 canonical URLs; **0 malformed/truncated**; 87 unique screen URLs cited (triangulation) |

---

## 2. Coverage audit — by CosFan group

Legend — **Strength:** Strong / Acceptable / Weak / Missing. **Visual ref:** all groups are *source-pointer only* (Mobbin URLs); no saved screenshots anywhere, so "visual" = "open the URL". **MVP / Risk / Pointer quality:** High / Med / Low.

| # | Group | Notes | Source apps | Strength | MVP action | Risk notes | Pointer | Notes |
|---|-------|:----:|-------------|----------|:----------:|:----------:|:-------:|-------|
| 1 | Onboarding | 6 | Spotify, Yahoo News, Flo, Clubhouse, Duolingo×2 | **Strong** | High | High | High | Follow-grid + interest-chips + value-prop + push-priming all covered. |
| 2 | Home / Explore | 6 | Pinterest×2, Depop×2, Instagram, YouTube | **Strong** | High | High | High | Masonry, creators-rail, category chips, sectioned browse. |
| 3 | Creator Profile / Membership | 6 | Patreon×3, Instagram, Substack, Depop | **Strong** | High | High | High | Pastel profile, tier picker, free/paid peers, trust layer. |
| 4 | Subscription / Billing | 6 | Patreon, Duolingo×2, Netflix×2, Calm | **Strong** | High | High | High | Paywall, honest cancel, billing state, plan picker, renewal reminder. |
| 5 | Lookbook / Content | 6 | Instagram×2, Patreon×2, Substack, Weverse | **Strong** | High | High | High | Was **0 in pack**; now **2 promoted** (locked post + Weverse fan post). |
| 6 | Message Channel | 5 | Instagram×2, Cameo, WhatsApp, Discord | **Strong** | High | High | High | Async 1:N broadcast; voice/video/live/presence excluded on purpose. |
| 7 | Photocard Collection | 6 | Artsy×2, Klarna, Instagram, Reddit, Pinterest | **Strong** | High | High | High | Owned-register grid+detail; all NFT/marketplace discarded. |
| 8 | Event Notice | 6 | Eventbrite×2, Nextdoor, adidas, Saturn, Luma | **Strong** | High | High | High | Date-first anatomy, free RSVP, safe-location states. |
| 9 | Safety / Report / Block | 6 | Discord, NGL, Instagram, Threads, Nextdoor, YouTube | **Strong** | High | High | High | Graduated block, post-report reassurance, status pipeline. |
| 10 | My / Settings | 4 | Mimo, Gentler Streak, Instagram, Coffee Meets Bagel | **Acceptable** | High | High | High | Low-novelty iOS idiom; 4 is sufficient. CMB = structure only (dating stripped). |
| 11 | Admin / Ops | 3 | Spotify for Creators, YouTube Studio, GroupMe | **Acceptable** (thinnest) | High | Med-High | High | Intentionally MVP-light; matches "fan-facing B2C, not creator SaaS" scope cap. |

**Totals:** 60 notes · ~48 distinct source apps-instances · every group ≥3 notes.

### Per-group detail

**Strong groups (1–9):** Each has 5–6 notes spanning 4–6 source apps, a concrete CosFan-specific MVP action, and explicit risk notes tied to a hard exclusion (anti-PPV / anti-NFT / anti-paid-DM / anti-dating / anti-call). Source pointers are canonical and verified. These are design-ready as *pattern* input.

**Group 10 — My / Settings (Acceptable):** 4 notes, 4 apps. Settings is a low-novelty iOS grouped-list idiom; the set (grouped hub + danger zone, two-axis notifications, privacy-as-questions, account toggles) covers the MVP surface. Coffee Meets Bagel is correctly flagged "structure only — dating semantics stripped." No gap that blocks design.

**Group 11 — Admin / Ops (Acceptable, thinnest):** 3 notes, 3 apps. This is the only sub-4 group, but it is **intentionally** light — the index caps admin ambition ("MVP-light, not a SaaS console"). The trio (glanceable overview / moderation queue / member management) covers the MVP admin surface. *Optional* future add if admin scope grows: a notice/announcement-composer screen and a creator payout/earnings state — neither is in MVP, so not a blocker.

### Missing apps / patterns (acknowledged, not blocking)

These are documented in the index's "Known gaps" and are **design-from-first-principles**, not collection failures:
- No pastel/collectible **cosplay-native** exemplar for any screen — CosFan's visual expression is its differentiation, so it has no Mobbin precedent by design.
- No true **owned digital photocard with edition framing minus commerce** — compose from Artsy (detail/grid) + Reddit (non-NFT rarity/provenance) + Klarna (surface).
- No strong wholesome-B2C **Community Guidelines / Safety Center** exemplar (results skewed dating/legal) — structural hints only.
- No in-app **card-entry / payment-method** screen (apps defer to App Store) — out of MVP scope anyway.

### Quality verdict (§2 fields, rolled up)

- **MVP action quality — HIGH.** Concrete and build-ready (e.g. "vertical stack of pastel tier cards: name → monthly price → 3–5 perk bullets → Join-per-card"), each re-skinned to CosFan, not a generic restatement.
- **Risk notes quality — HIGH (standout strength).** Every group names the specific banned-adjacent failure mode and the corrective framing. This is what makes the pack *safe* input.
- **Source pointer quality — HIGH.** 60/60 canonical `mobbin.com/(screens|flows)/<uuid>` URLs, zero truncation (the v0 truncated-URL pitfall is resolved).

---

## 3. Curated pack audit

Source: `curated/CLAUDE_DESIGN_INPUT_PACK/README.md`.

- **Count:** was **24** (within the 16–24 target). **Now 26** after the fix below.
- **Source pointer / local path per ref:** YES — every entry has both a relative note path and a Mobbin URL, plus a per-ref *Use for / Avoid* line.
- **Balance vs CosFan core product:** Good. Defers money below the fold, free+paid as peers, membership-not-PPV, broadcast-not-chat, owned-not-traded — the cross-cutting principles map directly to the hard exclusions.
- **Over/under-representation check (as the task asked):**

| Group | Recommended mix | Pack (v0) | Pack (now) | Status |
|---|:---:|:---:|:---:|---|
| Onboarding / Interest | 2–3 | 3 | 3 | OK |
| Home / Explore | 2–3 | 3 | 3 | OK |
| Creator Profile / Membership | 3 | 3 | 3 | OK |
| Membership / Subscription / Billing | 3 | 3 | 3 | OK |
| Message Channel | 2 | 2 | 2 | OK |
| **Lookbook / Content** | **2** | **0** | **2** | **FIXED** |
| Photocard Collection | 3 | 3 | 3 | OK |
| Event Notice | 2–3 | 3 | 3 | OK |
| Safety / Report / Block | 2 | 2 | 2 | OK |
| My / Settings or Admin / Ops | 1–2 | 2 | 2 | OK |
| **Total** | 22–26 | **24** | **26** | within envelope |

  - **No** over-representation of Safety/Billing/Profile (each at its recommended count, not above).
  - **No** under-representation of Photocard/Event/Home/Onboarding (each at top of its range).
  - The **only** deviation was **Lookbook/Content = 0** — now fixed.
- **Banned-adjacent references:** NONE. The pack explicitly excludes NFT/crypto, voice/video/live-call, dating-swipe, adult/PPV, marketplace. Spot-checked: nothing reads as adult PPV, private DM, dating, NFT, trading, or video call. The two highest-risk additions (locked-post, Weverse fan post) carry CRITICAL risk notes pinning them to membership-not-PPV and public-reply-not-paid-DM.

### Fix applied — promoted to the pack (Lookbook / Content, 2)

1. **Patreon — members-only locked post** (`raw/lookbook_content/patreon-members-only-locked-post.md`) — the locked/conversion state: frosted thumbnail + visible title/caption + value-tally + ONE membership CTA. Was already flagged in the index as the top hold-out candidate.
2. **Weverse — fan post detail** (`raw/lookbook_content/weverse-fan-post-detail.md`) — the unlocked, fandom-native consumption state + elevated "Artist's/Creator's comments" presence block (closeness via public reply, never paid DM). Closest tonal match to CosFan.

Rationale: these two are the *content-consumption* spine (locked → join, unlocked → read + feel close) that Profile and Photocard do not cover. Picking these two over the other four Lookbook notes avoids overlap (IG single-post/comments overlap Profile-grid interactions; Substack/Patreon-member are subsets).

> **Deviation logged:** pack is now **26**, two above the skill's "≤24" guidance. This honors the task's explicit recommended mix (Lookbook/Content: 2), whose envelope is 22–26. Acceptable and intentional.

---

## 4. Visual evidence check

- **Markdown-only?** YES — confirmed by `find ... -iname '*.png' -o ...` → 0 results; 464 KB total.
- **Classification:** *UX/IA pattern pack, not a full visual design pack.* Not a failure — screenshots were never saved by design (policy + asset-copyright boundary).
- **Can Mobbin MCP add legitimate visual evidence?** NO export path:
  - `search_screens` / `search_flows` → inline images **for the agent to view**, plus a `mobbin_url`. No download/export-to-file capability.
  - MCP resources = `ui://mobbin/search-screens.html` + `ui://mobbin/search-flows.html`, both `text/html;profile=mcp-app` interactive galleries — **not** downloadable screenshot assets.
  - Saving the inline images to disk would mean **copying Mobbin's proprietary screenshots**, which the guardrails, the mining skill ("never save/commit screenshots"), and the operating rules ("do not copy competitor UI or assets") all forbid.
- **Therefore:** no `visual/` image directory was created. Visual evidence is delivered as **`VISUAL_REFERENCE_MANIFEST.md`** — a per-reference visual-inspection brief (open-the-URL guide) for all 26 curated refs.

---

## 5. Minimum visual coverage gate (before Claude Design)

Gate rule: a required screen passes if the curated pack has **either a screenshot or a source pointer**.

| Required screen | Covered by (pack ref → Mobbin URL) | Pass |
|---|---|:--:|
| Creator profile / membership entry | Patreon pastel profile + IG profile grid | ✅ pointer |
| Tier / paywall / plan selection | Patreon tier picker + Patreon paywall + Duolingo plan picker | ✅ pointer |
| Active subscription / manage membership | Netflix billing state (+ Netflix manage in index) | ✅ pointer |
| Post-report confirmation **or** block sheet | NGL report confirmation + Discord/IG block | ✅ pointer |
| Photocard collection / detail | Artsy grid + Artsy detail (+ Klarna surface) | ✅ pointer |
| Event notice detail | Eventbrite free detail + Nextdoor RSVP + adidas rows | ✅ pointer |
| Home / explore **or** onboarding | Pinterest/Depop/YouTube + Spotify/Yahoo/Flo | ✅ pointer |

**All 7 required screens have source pointers → Claude Design readiness = READY (conditional).**
Conditions to state to Claude Design: (a) it is a *pattern/IA* pack — open the Mobbin URLs in the manifest, do not expect saved screenshots; (b) the **pastel/collectible visual expression is design-from-scratch** (no precedent, by design); (c) obey the hard exclusions on every screen.

---

## 6. Commit safety recommendation

**Do not commit now** (no explicit request). When asked, the following is safe and self-consistent:

**Safe to commit (all text, 464 KB, URL pointers only):**
- `references/mobbin/raw/**/*.md` (60 notes)
- `references/mobbin/MOBBIN_REFERENCE_INDEX.md`
- `references/mobbin/STATUS.md`
- `references/mobbin/curated/CLAUDE_DESIGN_INPUT_PACK/README.md`
- `references/mobbin/AUDIT.md` (this file)
- `references/mobbin/curated/CLAUDE_DESIGN_INPUT_PACK/VISUAL_REFERENCE_MANIFEST.md`
- `docs/skills/mobbin-reference-mining.md`
- `.gitkeep` scaffolding

**Likely local-only / gitignore:** none required — **no screenshots, no image dumps, no downloaded proprietary assets exist.** If screenshots are ever added later, they should be `.gitignore`d and kept local (proprietary Mobbin assets must not be committed).

**Must never commit:** Mobbin auth tokens/artifacts (none present), any saved competitor screenshots/assets.

---

## Readiness statement

**Reference Collection v0 is a strong, safe UX/IA pattern pack and is READY to seed Claude Design** under the three stated conditions. It is deliberately not a pixel/visual pack; the visual layer is CosFan's own design work. The single coverage weakness (Lookbook/Content) is resolved.
