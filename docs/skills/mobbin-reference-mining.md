# Skill: Mobbin Reference Mining (CosFan)

Reusable process for collecting Mobbin UI references into benchmark notes + a curated
design input pack. Created after **Mobbin Reference Collection v0** (2026-06-15).

Use this whenever a CosFan sprint needs Mobbin pattern-mining for design input.

---

## 0. Preflight gate (do NOT skip)
Mobbin MCP requires auth and **silently appears "registered but unusable"** until then.
1. `claude mcp list` → confirm `mobbin: ... ✔ Connected`. If it says `! Needs authentication`, STOP.
2. Fix: user runs `/mcp` → select **mobbin** → Authenticate (browser OAuth). Re-check `claude mcp list`.
3. Never paste/store the token; never commit auth artifacts; never use Playwright to bypass Mobbin auth.
4. Only after `✔ Connected` does the toolset change: `mcp__mobbin__authenticate` disappears and
   `mcp__mobbin__search_screens` + `mcp__mobbin__search_flows` become available (load via ToolSearch).

## 1. Tool facts
- `search_screens(query, platform, limit≤30, mode)` → screens w/ inline image + `mobbin_url`. Use `mode:"deep"` for nuance.
- `search_flows(query, platform, limit≤10, page)` → ordered screen sequences w/ images.
- **platform = "ios"** for CosFan (mobile-first). Don't put platform in the query string.
- One screen/flow per query; no negations; no vague style words; name an app to filter ("Patreon paywall").
- **You must examine the returned images** — metadata alone is not enough to write a note.

## 2. Fan-out collection pattern (what worked)
- One `general-purpose` subagent **per CosFan screen group**, ~2 waves of 5 (avoids rate-limit hammering + lets you QC wave 1).
- Each agent gets: CosFan context + visual guardrails + **its own AVOID list** + the benchmark template + the exact `raw/<group>/` write path + a fixed return format.
- Each writes to a **distinct folder** → no write collisions. Agents return compact text summaries (no images) → main context stays small.
- Main thread synthesizes the index + curated pack; agents do NOT.

## 3. CosFan AVOID lists (these banned types KEEP surfacing — pre-load every agent)
- **Photocard / collection queries → NFT/crypto/marketplace** (OpenSea, Rarible, Fanatics Live, Parallel). Discard anything with price/bids/resale/transfer/"Send". Keep the OWNED register only.
- **Message-channel queries → voice/video/live-call + presence** (Discord VC, IG Live, "Active now"/green dots, "join call"). Channel is async 1:N broadcast, no presence, no calls.
- **Profile/membership/content → PPV + 1:1 paid chat + adult.** Locked content = open membership join, never per-item purchase or pay-to-DM.
- **Onboarding/explore → casting-directory / dating-swipe / shopping-marketplace.** Keep handle+genre labels; strip cart/price/sort-by-price.
- **Settings → dating-category bleed** (Coffee Meets Bagel etc.): borrow list STRUCTURE only, strip semantics.
- **Event → paid ticketing/checkout + private-meetup/dating-meet.** Capture info density + free RSVP; gate exact addresses.

## 4. Benchmark note template (one file per useful reference)
Path: `references/mobbin/raw/<group>/<app>-<pattern-slug>.md`. Source pointer = the `mobbin_url`.
Fields: source_app, mobbin_category, screen_type, target_cosfan_screen, user_job,
first_visible_promise, primary_cta, secondary_cta, section_order, trust_elements,
friction_removed, empty_loading_error_handling, monetization_exposure, onboarding_step,
mobile_pattern, why_relevant_to_cosfan, what_to_learn, what_not_to_copy, risk_notes,
MVP_action, local_reference_path_or_source_pointer.
Weave in: what it says / who it persuades / why placed here / what friction it cuts / what action it drives / reuse? / modify? / avoid? / apply to MVP?

## 5. Outputs
- `references/mobbin/MOBBIN_REFERENCE_INDEX.md` — all notes grouped by the 11 CosFan screen groups.
- `references/mobbin/curated/CLAUDE_DESIGN_INPUT_PACK/README.md` — **16–24** selected, design-ready, self-contained brief (positioning + hard exclusions + palette guardrails + the picks + cross-cutting principles + "design from scratch" gaps).
- **Never** save/commit screenshots; notes carry `mobbin_url` pointers only. Keep the pack ≤24 — do not dump all raw refs.

## 6. Verification checklist
- `git status --short --branch` (new files untracked; nothing staged/committed unless asked).
- Per-group note count; `find references/mobbin -type f | wc -l`; `du -sh references/mobbin` (should be small KB — if MB, screenshots leaked in).
- **Extract URLs from the files, don't hand-copy them into the index** (see Pitfall A).

---

## Pitfalls learned (v0)
- **A. Index URL transcription is error-prone.** Hand-copying 60 `mobbin_url`s from subagent prose into the index introduced a truncated URL. **Fix:** after agents finish, `grep -h "local_reference_path_or_source_pointer" references/mobbin/raw/**/*.md` to pull canonical URLs straight from the notes, and build/verify the index against that — don't retype from chat summaries.
- **B. Recommended curated mix omitted Lookbook/Content** (overlaps Profile + Photocard). Honor the mix but flag the top hold-out (`patreon-members-only-locked-post.md`) in the index so it's not lost.
- **C. `.gitkeep` placeholders** appear in scaffolded dirs and inflate `find -type f` counts. Count `*.md` separately when reporting note totals.
- **D. "Collectible" is the single highest-risk query** — it pulls NFT/marketplace results almost every time. Always pair it with an explicit non-NFT discard rule and a light-theme/provenance framing.
