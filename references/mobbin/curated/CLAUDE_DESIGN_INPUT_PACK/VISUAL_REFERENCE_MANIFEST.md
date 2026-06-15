# CosFan — Visual Reference Manifest (Claude Design Input Pack)

Per-reference **visual-inspection brief** for all 26 curated references. Each brief captures
the *structure / IA / spacing / density* to transfer, then re-skin to "Cool Pastel Collectible
OS." Read the linked local note for full section order.

> **Source pointers are provenance only.** The `mobbin_url` on each row records where the
> pattern was found. It is **not guaranteed to open outside the authenticated Mobbin
> MCP/session** (the links were tested and do not reliably open) and is **not sufficient as
> Claude Design visual input**. **Manual screenshot capture or an MCP-derived visual board is
> required before Claude Design** — see `PIXEL_CAPTURE_REQUIRED.md` and
> `MANUAL_SCREENSHOT_QUEUE.md`. Use these written briefs as the IA/pattern layer; do not rely on
> opening the URLs.

## Why there are no saved screenshots (applies to every entry below)

- **Screenshot:** absent for all 26 — by policy and capability.
- **Why:** Mobbin MCP (`search_screens` / `search_flows`) returns inline images **for
  on-screen viewing only**; its only resources are two `text/html;profile=mcp-app`
  galleries — there is **no screenshot/image export-to-file** capability. Saving those
  inline images would mean **copying Mobbin's proprietary screenshots**, which the CosFan
  guardrails, the mining skill ("never save/commit screenshots"), and the operating rules
  ("do not copy competitor UI or assets") forbid. We were authenticated and could view
  every screen; we deliberately did not extract assets.
- **Consequence:** this is a **UX/IA pattern pack, not a pixel pack** — and a pattern pack is
  **not sufficient as Claude Design visual input** on its own. The source-pointer URLs are
  **provenance only** and are **not guaranteed to open outside the authenticated Mobbin
  MCP/session**, so they cannot be handed to Claude Design. **Manual screenshot capture or an
  MCP-derived visual board is required before Claude Design** (see `PIXEL_CAPTURE_REQUIRED.md`).

> Global density target for every re-skin: **white-first canvas, airy 2-col, pastel
> blue/mint/lavender/lilac accents (chips/states only, not big fills), soft rounded cards
> with restrained elevation, iOS-native idioms. No beige/cream/sepia, no glassmorphism, no
> 3D icons, no heavy shadows, no marketplace/presence/call chrome.**

---

## Visual evidence status — machine-readable (added 2026-06-15)

**Live probe (2026-06-15):** ran `mcp__mobbin__search_screens` and
`mcp__mobbin__search_flows` against the authenticated Mobbin MCP. Both return **inline
preview images + a `mobbin_url` + a proprietary `https://mobbin.com/api/mcp/short/…` image
link — and nothing else.** `ListMcpResourcesTool` shows only two
`text/html;profile=mcp-app` inline galleries; there is **no file/screenshot export
resource.** The flow probe resolved a live Patreon flow `fdde05b8-…` = ref 7 **inside the
authenticated MCP session only** — the same URLs are **provenance only** and are **not
guaranteed to open outside that authenticated Mobbin MCP/session** (the user tested them and
they do not reliably open). Conclusion: **images are viewable inline, not exportable, and the
URLs are not portable design input.** Persisting the `api/mcp/short` asset to disk would copy
Mobbin's proprietary screenshot — forbidden by the CosFan guardrails, the mining skill, and the
operating rules. We did not.

- **copyright_note (every row):** reference for internal pattern study only; do not copy or
  redistribute Mobbin UI/assets. Source pointers are **provenance only** — they link out to
  Mobbin, are **not guaranteed to open outside the authenticated Mobbin MCP/session**, and are
  **not sufficient as Claude Design visual input**. No asset is stored here.
- **Field mapping:** `source_app` · `screen_or_flow_name` · `target_cosfan_screen` ·
  `source_pointer` · `local_visual_path` · `manual_capture_needed` → the table below.
  `visual_pattern_to_inspect` · `layout_density_notes` · `color_or_spacing_notes` ·
  `what_claude_design_should_learn` · `what_claude_design_must_not_copy` → the per-reference
  briefs in the sections that follow (Inspect / Layout-density / Learn / Don't-copy lines;
  global re-skin palette in the density-target note above).

| # | source_app | screen_or_flow_name | target_cosfan_screen | source_pointer | local_visual_path | manual_capture_needed |
|---|---|---|---|---|---|---|
| 1 | Spotify | Pick favorite artists grid (flow) | Onboarding "follow 3+ creators" | https://mobbin.com/flows/2ca9968b-a50d-4910-89e7-e894023d7d21 | MISSING | yes |
| 2 | Yahoo News | Select 5+ topics grid (screen) | Genre/interest multi-select | https://mobbin.com/screens/edd230f6-18a7-4a4a-a8d8-4a6a56ffcb01 | MISSING | yes |
| 3 | Flo | Value-proposition intro (screen) | Screen-one positioning | https://mobbin.com/screens/37b688e4-33a8-4e1c-9350-16214da4cf39 | MISSING | yes |
| 4 | Pinterest | Masonry feed + filter chips (screen) | Explore / browse feed | https://mobbin.com/screens/c41c75fe-19ba-4cc8-837c-91628a3bb493 | MISSING | yes |
| 5 | Depop | "Creators to watch" rail + grid (screen) | Explore w/ people rail | https://mobbin.com/screens/077eb5df-3011-4a04-baf2-b1818c7ad1f8 | MISSING | yes |
| 6 | YouTube | Home feed + category chips (screen) | Followed-creator home | https://mobbin.com/screens/d12ba72a-6af0-4143-9f9c-ac5e5a3cd1bb | MISSING | yes |
| 7 | Patreon | Pastel profile + upgrade entry (flow) | Creator profile + membership entry | https://mobbin.com/flows/fdde05b8-ae13-4cc1-a4b4-1ce14efad3dc | MISSING | yes |
| 8 | Patreon | Tier picker, vertical cards (screen) | Tier comparison + join | https://mobbin.com/screens/c4f9b3b6-ea7e-42da-a88c-4dd01690970e | MISSING | yes |
| 9 | Instagram | Creator profile grid (screen) | Profile mental model | https://mobbin.com/screens/55fae9cc-be5b-460c-97f6-1b02e6b07bef | MISSING | yes |
| 10 | Patreon | Tier membership paywall (screen) | Subscribe sheet | https://mobbin.com/screens/bb6be2c9-4152-4a0a-8906-71f6770a4ab2 | MISSING | yes |
| 11 | Duolingo | Honest cancellation flow (flow) | Cancel membership flow | https://mobbin.com/flows/4aeb8ce4-9295-42e4-bc11-13c32c752698 | MISSING | yes |
| 12 | Netflix | Account billing state (screen) | Active subscription / manage | https://mobbin.com/screens/d903b372-13ed-4905-b2d1-450b2666326d | MISSING | yes |
| 13 | Patreon | Members-only locked post (screen) | Locked lookbook post | https://mobbin.com/screens/44913b43-97a0-4ced-bfaa-997f5b3337d2 | MISSING | yes |
| 14 | Weverse | Fan post detail (screen) | Unlocked post detail | https://mobbin.com/screens/bbc725cf-0014-41d4-8330-91fb9bced4ff | MISSING | yes |
| 15 | Instagram | Broadcast channel feed (screen) | 1:N creator→fans channel | https://mobbin.com/screens/77621fdc-6426-4763-9ff8-1882eb751de5 | MISSING | yes |
| 16 | Cameo | Creator→fans update feed (screen) | Channel header + hierarchy | https://mobbin.com/screens/c8ba38fd-432c-4cc2-8df9-f99fc04099f8 | MISSING | yes |
| 17 | Artsy | Saved artworks grid (screen) | Photocard collection grid | https://mobbin.com/screens/7e81ec53-2904-4e06-bb1f-4b58ee067b1b | MISSING | yes |
| 18 | Artsy | Artwork detail (screen) | Single photocard detail | https://mobbin.com/screens/72878c05-7a51-4e00-886f-1bf0a1a09365 | MISSING | yes |
| 19 | Klarna | Saved items grid (screen) | Collection surface + empty state | https://mobbin.com/screens/9a2a7793-6ead-4d5d-b370-5d61059450b9 | MISSING | yes |
| 20 | Eventbrite | Free event detail (screen) | Event notice detail | https://mobbin.com/screens/46099065-c93f-42d6-9293-f4f8f9ff9a83 | MISSING | yes |
| 21 | Nextdoor | Community event RSVP (screen) | Free RSVP control | https://mobbin.com/screens/52830538-46ab-4432-9980-9162aa8cd761 | MISSING | yes |
| 22 | adidas Running | Structured event detail (screen) | Event anatomy + honest gate | https://mobbin.com/screens/fdaf7dbf-34d1-4610-89ec-96de84bcbd3d | MISSING | yes |
| 23 | Discord | Graduated ignore/block (screen) | Graduated safety sheet | https://mobbin.com/screens/0acc46bb-ea2c-46aa-b95e-059671116efc | MISSING | yes |
| 24 | NGL | Report confirmation + safety resources (screen) | Post-report confirmation | https://mobbin.com/screens/0932f2c5-3f29-4da3-8042-c85170e7f73f | MISSING | yes |
| 25 | Gentler Streak | Notification settings, Push/Email (screen) | Notification settings | https://mobbin.com/screens/33a9da03-3400-445d-9e4e-943e33d1f2de | MISSING | yes |
| 26 | Spotify for Creators | Comment moderation queue (screen) | MVP admin / moderation | https://mobbin.com/screens/db770b06-a394-4ba3-95ab-db5183c8d997 | MISSING | yes |

### How to manually capture (REQUIRED before Claude Design)

Source pointers are provenance only and are not sufficient as Claude Design visual input, so
stored screenshots (or an MCP-derived visual board) are **required** before Claude Design.
Capture them yourself from a licensed Mobbin session — do not have the agent extract them.
See `MANUAL_SCREENSHOT_QUEUE.md` for the prioritized 12–16 capture targets:

1. Open the row's `source_pointer` URL in a browser logged into your own Mobbin account.
2. Confirm your Mobbin plan permits the intended internal use (check their ToS).
3. Use your OS screenshot tool on a screen you are licensed to view.
4. Save into `visual-local/` using the queue's target filename
   (e.g. `visual-local/04-membership-tier-paywall.png`); see `MANUAL_SCREENSHOT_QUEUE.md`.
5. Set that row's `local_visual_path` to the saved path and `manual_capture_needed` to `no`.
6. Keep `visual-local/` **local-only** (recommend git-ignoring it) — proprietary screenshots
   must not be committed.

The agent must NOT: use Playwright/headless to bypass Mobbin auth, scrape unauthenticated
pages, fetch the `api/mcp/short` asset to disk, or store cookies/tokens/credentials.

---

## Onboarding / Interest

### 1. Spotify — pick favorite artists grid
- **Source pointer (provenance only):** https://mobbin.com/flows/2ca9968b-a50d-4910-89e7-e894023d7d21 · **Note:** `../../raw/onboarding/spotify-pick-favorite-artists-grid.md`
- **Target CosFan screen:** Onboarding "follow 3+ creators" step.
- **Inspect:** the photo-tile selection grid, the header minimum ("Choose 3+"), per-tile selected state, and the sticky bottom CTA that stays disabled until the minimum is met.
- **Layout / density:** ~3-col circular/rounded portrait tiles, tight gutters, label under each tile; persistent header count + sticky footer CTA. CosFan: go airier, rounded-square creator tiles on white, pastel selected-ring.
- **Learn:** header-stated minimum + gated sticky CTA kills "have I done enough?" anxiety and seeds cold-start personalization.
- **Don't copy:** Spotify's dark theme, dense packing, or any read that turns portraits into a casting directory — keep handle + genre labels, zero book/meet/price.

### 2. Yahoo News — select 5+ topics grid
- **Source pointer (provenance only):** https://mobbin.com/screens/edd230f6-18a7-4a4a-a8d8-4a6a56ffcb01 · **Note:** `../../raw/onboarding/yahoo-news-select-5-topics-grid.md`
- **Target CosFan screen:** Genre/interest multi-select (cosplay series, idol, photoshoot styles).
- **Inspect:** chip/topic grid, multi-select toggle states, reassurance microcopy, minimum + sticky CTA.
- **Layout / density:** wrap-flow of pill chips or labeled tiles; clear selected vs unselected contrast; comfortable tap targets. CosFan: pastel chip fills on selection, generous spacing.
- **Learn:** interest capture as low-effort chips with a stated minimum and "change anytime" reassurance.
- **Don't copy:** news-brand styling, dense list framing.

### 3. Flo — value-proposition intro
- **Source pointer (provenance only):** https://mobbin.com/screens/37b688e4-33a8-4e1c-9350-16214da4cf39 · **Note:** `../../raw/onboarding/flo-value-proposition-intro.md`
- **Target CosFan screen:** Screen-one positioning ("Bubble + Patreon + photocard").
- **Inspect:** single-screen composition — headline, exactly 3 benefit rows (icon + short line), one primary CTA.
- **Layout / density:** vertical rhythm with one headline block + three evenly spaced benefit rows + one CTA; lots of whitespace, no scroll needed. CosFan: pastel benefit-row icons, white canvas.
- **Learn:** open with one calm value-prop; exactly 3 benefits; defer questions/paywall.
- **Don't copy:** health-app imagery, "get closer to her"/deals/crypto wording.

---

## Home / Explore

### 4. Pinterest — masonry feed + filter chips
- **Source pointer (provenance only):** https://mobbin.com/screens/c41c75fe-19ba-4cc8-837c-91628a3bb493 · **Note:** `../../raw/home_explore/pinterest-masonry-feed-with-filter-chips.md`
- **Target CosFan screen:** Explore / browse feed.
- **Inspect:** top horizontal filter-chip rail + image-first masonry grid; minimal chrome.
- **Layout / density:** 2-col staggered masonry, very dense, tiny gutters. **CosFan goes airier:** 2-col with white gutters, larger rounded corners, fewer items per fold.
- **Learn:** one image-first feed serves many tastes via a top chip rail.
- **Don't copy:** Pinterest's high density, save-button chrome; do not bind tiles to commerce.

### 5. Depop — "creators to watch" rail + grid
- **Source pointer (provenance only):** https://mobbin.com/screens/077eb5df-3011-4a04-baf2-b1818c7ad1f8 · **Note:** `../../raw/home_explore/depop-sellers-to-watch-then-grid.md`
- **Target CosFan screen:** Explore with a curated people rail above content.
- **Inspect:** horizontal avatar rail ("people to watch") sitting above the content grid; editorial section title.
- **Layout / density:** circular-avatar horizontal scroller (name under each) → grid below. CosFan: pastel-ring avatars, "Creators to watch" title.
- **Learn:** lead discovery with a curated *people* rail before the content firehose — keeps explore feeling like fan-membership.
- **Don't copy:** ALL marketplace/price/cart chrome, sort-by-price.

### 6. YouTube — home feed + category chips
- **Source pointer (provenance only):** https://mobbin.com/screens/d12ba72a-6af0-4143-9f9c-ac5e5a3cd1bb · **Note:** `../../raw/home_explore/youtube-home-feed-category-chips.md`
- **Target CosFan screen:** Followed-creator home.
- **Inspect:** sticky horizontal category chips under the header; authored content cards each bound to a creator (avatar + name); inline non-blocking states.
- **Layout / density:** single-column authored cards with creator row on each; sticky chip rail. CosFan: 1-col or 2-col pastel cards, creator avatar on every card.
- **Learn:** authorship + one-tap topic chips make a followed-creator home scannable.
- **Don't copy:** video/Shorts chrome, red brand accents.

---

## Creator Profile

### 7. Patreon — pastel profile + upgrade entry
- **Source pointer (provenance only):** https://mobbin.com/flows/fdde05b8-ae13-4cc1-a4b4-1ce14efad3dc · **Note:** `../../raw/creator_profile_membership/patreon-pastel-profile-upgrade-entry.md`
- **Target CosFan screen:** Creator profile + membership entry (closest tonal match).
- **Inspect:** profile header (cover + avatar + name + descriptor), an "Upgrade membership" entry, and a locked-post teaser conveying value; the soft pastel tonal treatment.
- **Layout / density:** cover banner → centered identity block → membership CTA → posts; calm header, money below the fold. CosFan: this is the nearest existing tone — still re-skin to its own palette.
- **Learn:** identity + social proof first; membership entry + locked teaser convey value without a hard wall.
- **Don't copy:** "patron/pledge" vocabulary, Patreon orange/coral, exact card composition.

### 8. Patreon — tier picker (vertical cards)
- **Source pointer (provenance only):** https://mobbin.com/screens/c4f9b3b6-ea7e-42da-a88c-4dd01690970e · **Note:** `../../raw/creator_profile_membership/patreon-tier-picker-checkout.md`
- **Target CosFan screen:** Tier / benefit comparison + join.
- **Inspect:** vertically stacked, self-contained tier cards (name → big price → perks → per-card Join), "Show more" progressive disclosure, optional custom-pledge escape hatch.
- **Layout / density:** full-width stacked cards, generous internal padding, one CTA per card — thumb-friendly, no horizontal price table. CosFan: pastel tier cards, 3–5 perk bullets, "Join this tier" per card.
- **Learn:** CTA travels with each option (no select-then-confirm); transparent price; progressive disclosure for long perk lists.
- **Don't copy:** "patron"/tax-label wording, pink-on-white chrome, per-DM/1:1 tier framing.

### 9. Instagram — creator profile grid
- **Source pointer (provenance only):** https://mobbin.com/screens/55fae9cc-be5b-460c-97f6-1b02e6b07bef · **Note:** `../../raw/creator_profile_membership/instagram-creator-profile-grid.md`
- **Target CosFan screen:** Profile mental model fans already know.
- **Inspect:** stats triad (posts/followers/…), Follow vs Subscribe as visual peer buttons, 3-col content grid.
- **Layout / density:** compact identity row + stats triad + two peer buttons + tight 3-col grid. CosFan: keep the peer buttons (free Follow + paid Join), loosen the grid to airy 2-col.
- **Learn:** free Follow and paid Join as visual peers = "open membership, not transactional".
- **Don't copy:** IG iconography, story-ring chrome, 3-col density.

---

## Membership / Subscription

### 10. Patreon — tier membership paywall
- **Source pointer (provenance only):** https://mobbin.com/screens/bb6be2c9-4152-4a0a-8906-71f6770a4ab2 · **Note:** `../../raw/subscription_billing/patreon-tier-membership-paywall.md`
- **Target CosFan screen:** Subscribe sheet.
- **Inspect:** price embedded **inside** the primary CTA, benefit bullets, real annual-save callout.
- **Layout / density:** bottom-sheet or full-screen with benefit list + one dominant CTA carrying the price. CosFan: pastel CTA "Start membership — $X/mo".
- **Learn:** price-in-CTA + concrete benefits + mathematically-real annual save.
- **Don't copy:** PPV per-item framing, brand color, fake strike-through.

### 11. Duolingo — honest cancellation flow
- **Source pointer (provenance only):** https://mobbin.com/flows/4aeb8ce4-9295-42e4-bc11-13c32c752698 · **Note:** `../../raw/subscription_billing/duolingo-cancellation-flow.md`
- **Target CosFan screen:** Cancel membership flow.
- **Inspect:** one-decision-per-screen sequence — reason survey, honest consequence, end-date, easy renew.
- **Layout / density:** single focal question per screen, plenty of whitespace, equal-weight Cancel/Keep. CosFan: same honest cadence, pastel.
- **Learn:** honesty as the pattern — one fair trade-off or a genuine Pause, never a guilt maze.
- **Don't copy:** mascot art; any dark-pattern (hidden cancel, pre-checked resubscribe).

### 12. Netflix — account billing state
- **Source pointer (provenance only):** https://mobbin.com/screens/d903b372-13ed-4905-b2d1-450b2666326d · **Note:** `../../raw/subscription_billing/netflix-account-billing-state.md`
- **Target CosFan screen:** Active subscription / manage membership.
- **Inspect:** plain-sentence next-billing-date, masked card, Cancel↔Restart as equal options.
- **Layout / density:** grouped-list rows, facts in one eyeline, no buried fine print. CosFan: iOS grouped list on white.
- **Learn:** state billing facts as plain sentences; Cancel one tap away and legitimate.
- **Don't copy:** Netflix red, dark theme, content-merchandising chrome.

---

## Lookbook / Content

### 13. Patreon — members-only locked post
- **Source pointer (provenance only):** https://mobbin.com/screens/44913b43-97a0-4ced-bfaa-997f5b3337d2 · **Note:** `../../raw/lookbook_content/patreon-members-only-locked-post.md`
- **Target CosFan screen:** Members-only lookbook post in its locked / conversion state.
- **Inspect:** the post card for a non-member — visible title + caption snippet + a **locked media thumbnail** (padlock over a branded/blurred tile), a single membership CTA, and a sibling "unlock N posts" tally.
- **Layout / density:** real post card (avatar + date + title + caption) with a frosted/locked media tile and a muted action row; ONE sticky membership button above the feed. CosFan: soft frosted card, cute pastel lock badge, "Join [creator] to unlock" + "Members see N posts".
- **Learn:** show enough metadata to build desire; quantify the unlock; route every locked tap to ONE membership join.
- **Don't copy (CRITICAL):** any "unlock this photo for $X" / tip-to-see; Patreon's lock-glyph/blur and orange mark; blur that reads as an adult/PPV teaser — keep it a clean "members only" frosted state.

### 14. Weverse — fan post detail
- **Source pointer (provenance only):** https://mobbin.com/screens/bbc725cf-0014-41d4-8330-91fb9bced4ff · **Note:** `../../raw/lookbook_content/weverse-fan-post-detail.md`
- **Target CosFan screen:** Unlocked creator post detail (fandom-native, idol→fan tone).
- **Inspect:** creator post at top (avatar + handle + verified + timestamp + caption + like/comment counts) → a distinct **"Artist's comments"** block surfacing the creator's own reply → "All comments (N)" fan list with per-comment like/reply → pinned bottom composer.
- **Layout / density:** photo-first post, then a visually elevated creator-reply block, then a threaded list; pinned composer. CosFan: pastel "Creator replied" block, affectionate reaction set.
- **Learn:** manufacture authentic closeness by elevating the creator's **public** reply into its own labeled block; per-comment likes for fan-to-fan warmth.
- **Don't copy (CRITICAL):** Weverse red chrome and exact tab labels; never imply a paid/private 1:1 DM — the creator's reply stays a public in-thread comment.

---

## Message Channel

### 15. Instagram — broadcast channel feed
- **Source pointer (provenance only):** https://mobbin.com/screens/77621fdc-6426-4763-9ff8-1882eb751de5 · **Note:** `../../raw/message_channel/instagram-broadcast-channel-feed.md`
- **Target CosFan screen:** Bubble-style 1:N creator→fans channel.
- **Inspect:** read-first message feed (every message creator-authored), one-tap reaction tallies, an honest join/notify gate ("added to your inbox, you'll get notifications").
- **Layout / density:** chat-like but broadcast-only stream; reaction chips under each message; no composer for fans. CosFan: pastel reaction chips, creator-only authorship.
- **Learn:** broadcast-only + reactions is what keeps it 1:N, not a fake 1:1 paid chat; honest join explainer removes spam fear.
- **Don't copy:** DMs, presence dots / "Active now", any call/live affordance.

### 16. Cameo — creator→fans update feed
- **Source pointer (provenance only):** https://mobbin.com/screens/c8ba38fd-432c-4cc2-8df9-f99fc04099f8 · **Note:** `../../raw/message_channel/cameo-creator-fan-update-feed.md`
- **Target CosFan screen:** Channel header + post hierarchy.
- **Inspect:** "<creator> + N fans" header framing 1:N; reaction-primary / comment-secondary hierarchy.
- **Layout / density:** header with member count, then update cards with reactions foregrounded. CosFan: pastel header, member count, reaction-first.
- **Learn:** header frames 1:N + trust; reactions primary, comments secondary.
- **Don't copy:** "going live / Cameo Call" semantics — layout only.

---

## Photocard Collection

### 17. Artsy — saved artworks grid
- **Source pointer (provenance only):** https://mobbin.com/screens/7e81ec53-2904-4e06-bb1f-4b58ee067b1b · **Note:** `../../raw/photocard_collection/artsy-saved-artworks-grid.md`
- **Target CosFan screen:** Photocard collection grid (OWNED register).
- **Inspect:** 2-col "Saved" grid, header count, quiet per-tile provenance captions, no price/marketplace pressure.
- **Layout / density:** clean 2-col image grid on white, caption under each tile, header count ("N cards"). CosFan: white-card-on-white, per-tile creator avatar chip.
- **Learn:** header count + provenance captions make a collection feel owned and motivate completion.
- **Don't copy:** any buy/price/sort; Artsy's editorial-serif tone.

### 18. Artsy — artwork detail
- **Source pointer (provenance only):** https://mobbin.com/screens/72878c05-7a51-4e00-886f-1bf0a1a09365 · **Note:** `../../raw/photocard_collection/artsy-artwork-detail.md`
- **Target CosFan screen:** Single photocard / object detail.
- **Inspect:** image-first hero, identity/provenance (title/artist/year/medium) **before** any price, Save confirmation.
- **Layout / density:** large hero image → metadata stack → Save; refined, sparse. CosFan: hero photocard, provenance line ("from [creator]'s drop, [date]"), no price.
- **Learn:** image-first + identity/provenance-before-price makes a single object read as a collectible record, not a buyable asset.
- **Don't copy:** buy/bid/inquire/transfer affordances, gallery-commerce chrome.

### 19. Klarna — saved items grid (surface match)
- **Source pointer (provenance only):** https://mobbin.com/screens/9a2a7793-6ead-4d5d-b370-5d61059450b9 · **Note:** `../../raw/photocard_collection/klarna-saved-items-grid.md`
- **Target CosFan screen:** Collection surface treatment + save toast + empty state.
- **Inspect:** white rounded-card-on-white tiles, per-tile creator/brand avatar chip, save toast, friendly empty state. **This is the closest existing surface to Cool Pastel Collectible OS.**
- **Layout / density:** white cards, soft corners, restrained elevation, airy gutters. CosFan: adopt this surface almost directly (re-skin accents to pastel).
- **Learn:** the exact white-card pastel surface + save toast + empty state.
- **Don't copy:** wishlist / save-to-buy / price semantics → use OWNED register only.

---

## Event Notice

### 20. Eventbrite — free event detail
- **Source pointer (provenance only):** https://mobbin.com/screens/46099065-c93f-42d6-9293-f4f8f9ff9a83 · **Note:** `../../raw/event_notice/eventbrite-free-event-detail.md`
- **Target CosFan screen:** Event notice detail (end-to-end).
- **Inspect:** hero → organizer row (avatar + name + Follow) → parsed date/time → add-to-calendar; "atmosphere → who → when → participate" order.
- **Layout / density:** hero image, then stacked labeled blocks, sticky participate CTA. CosFan: pastel, creator as the persuader high on the page.
- **Learn:** parsed date-first; organizer-as-persuader reframes the event as a creator broadcast.
- **Don't copy:** paid ticketing/checkout, ticket-tier tables.

### 21. Nextdoor — community event RSVP
- **Source pointer (provenance only):** https://mobbin.com/screens/52830538-46ab-4432-9980-9162aa8cd761 · **Note:** `../../raw/event_notice/nextdoor-community-event-rsvp.md`
- **Target CosFan screen:** Free RSVP control + honest attendance.
- **Inspect:** FREE label, single "Going/Interested/Not" RSVP dropdown, honest social proof (who's going).
- **Layout / density:** compact detail with one RSVP control; no ticketing. CosFan: pastel RSVP pill.
- **Learn:** a single RSVP control is enough for MVP; "announcement, not a sale".
- **Don't copy:** guest-invites-guest chains; exposed exact address (gate it).

### 22. adidas Running — structured event detail
- **Source pointer (provenance only):** https://mobbin.com/screens/fdaf7dbf-34d1-4610-89ec-96de84bcbd3d · **Note:** `../../raw/event_notice/adidas-running-structured-event-detail.md`
- **Target CosFan screen:** Information-dense event anatomy + honest gate.
- **Inspect:** labeled icon rows (Date / Time / What / Who-can-attend), explained members-only gate.
- **Layout / density:** icon + label + value rows stacked for scannability. CosFan: pastel row icons, explicit "Online" / "revealed to attendees" states.
- **Learn:** labeled icon rows maximize info density; explain any gate honestly.
- **Don't copy:** athletic-brand styling; paid-ticket framing.

---

## Safety / Report / Block

### 23. Discord — graduated ignore/block
- **Source pointer (provenance only):** https://mobbin.com/screens/0acc46bb-ea2c-46aa-b95e-059671116efc · **Note:** `../../raw/safety_report_block/discord-ignore-user-deescalation.md`
- **Target CosFan screen:** Graduated safety sheet (mute/get-space → block).
- **Inspect:** the "Ignore <user>?" de-escalation sheet — light option → hard block, honest statement of limits.
- **Layout / density:** bottom sheet naming the user, graduated options, plain consequence text. CosFan: pastel, supportive tone.
- **Learn:** offer a graduated model with honest limits so anxious users still set a boundary.
- **Don't copy:** surveillance/policing tone, Discord dark theme.

### 24. NGL — report confirmation + safety resources
- **Source pointer (provenance only):** https://mobbin.com/screens/0932f2c5-3f29-4da3-8042-c85170e7f73f · **Note:** `../../raw/safety_report_block/ngl-report-confirmation-safety-resources.md`
- **Target CosFan screen:** Post-report confirmation (the screen that makes CosFan *feel* safe).
- **Inspect:** success check + reassurance copy + inline Block + route to human help/safety resources.
- **Layout / density:** centered success state, reassurance paragraph, one-tap Block, help links. CosFan: pastel success, warm reassurance.
- **Learn:** post-report screen does the heaviest trust lifting — success + reassurance + inline Block + human help.
- **Don't copy:** over-promised enforcement (fake 24/7 "Safety Team"); NGL's neon styling.

---

## My / Settings + Admin / Ops

### 25. Gentler Streak — notification settings (Push/Email)
- **Source pointer (provenance only):** https://mobbin.com/screens/33a9da03-3400-445d-9e4e-943e33d1f2de · **Note:** `../../raw/my_settings/gentler-streak-notification-settings-push-email.md`
- **Target CosFan screen:** Notification settings.
- **Inspect:** two-axis layout — channel (Push vs Email) then per-type toggles; inline email destination; marketing as one clearly-labeled default-off switch separate from billing alerts.
- **Layout / density:** iOS grouped list, sectioned by channel, plain row labels + toggles. CosFan: calm grouped list on white.
- **Learn:** channel-first then per-type; marketing default-off and separated from billing.
- **Don't copy:** fitness-app accent styling.

### 26. Spotify for Creators — moderation queue
- **Source pointer (provenance only):** https://mobbin.com/screens/db770b06-a394-4ba3-95ab-db5183c8d997 · **Note:** `../../raw/admin_ops/spotify-for-creators-comment-moderation-queue.md`
- **Target CosFan screen:** MVP-light admin / moderation.
- **Inspect:** needs-review vs published tabs, per-item overflow action sheet, destructive confirm with stated consequence ("delete + also block" in one step).
- **Layout / density:** list of items with per-row overflow; tabbed split; confirm sheet. CosFan: keep it light, not a SaaS console.
- **Learn:** split needs-review vs published; confirm destructive actions; combine delete+block.
- **Don't copy:** SaaS-console density / dashboards-everywhere creep.

---

## Coverage vs the minimum-visual-coverage gate

All seven gate screens have a **source pointer (provenance only)** here. A source pointer is
**not guaranteed to open outside the authenticated Mobbin MCP/session** and is **not sufficient
as Claude Design visual input**:

| Required screen | Manifest refs |
|---|---|
| Creator profile / membership entry | 7, 9 |
| Tier / paywall / plan selection | 8, 10 |
| Active subscription / manage membership | 12 |
| Post-report confirmation / block sheet | 23, 24 |
| Photocard collection / detail | 17, 18, 19 |
| Event notice detail | 20, 21, 22 |
| Home / explore or onboarding | 1, 2, 3, 4, 5, 6 |

**Gate for Claude Design visual input = NOT satisfied.** Provenance is recorded for every gate
screen, but there are **0 local screenshots and no MCP-derived visual board**. Manual screenshot
capture or an MCP-derived visual board is required before Claude Design (see
`PIXEL_CAPTURE_REQUIRED.md` and `MANUAL_SCREENSHOT_QUEUE.md`). Visual expression remains
design-from-scratch.
