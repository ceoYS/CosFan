# CosFan — Manual Screenshot Queue

**Why this exists:** Mobbin source pointers are **provenance only** — not guaranteed to open
outside the authenticated Mobbin MCP/session, and not sufficient as Claude Design visual input
(see `PIXEL_CAPTURE_REQUIRED.md`). To unblock Claude Design, the user manually captures the
screens below from a licensed Mobbin session.

**How to use this queue**
- Do **not** rely on the old URLs — they may not open. Instead, open Mobbin, search the
  **source app**, and find the screen matching the **pattern to capture**.
- Save each capture into `visual-local/` using the exact **target filename**.
- Keep `visual-local/` **local-only** (recommend git-ignoring it). Manual captures of Mobbin's
  proprietary screens must not be committed.
- After saving, update the matching row in `VISUAL_REFERENCE_MANIFEST.md`
  (`local_visual_path` + `manual_capture_needed: no`).

**Capture format:** iPhone-proportion (portrait), full screen, light mode where the app offers
it. 12 core targets below; 4 optional stretch targets after.

---

## Core 12 (capture these first)

### 1. Onboarding / interest
- **Target filename:** `01-onboarding-interest-grid.png`
- **Source app (search in Mobbin):** Spotify (iOS) — fallback: Yahoo News
- **Pattern to capture:** the "pick your favorite artists" multi-select **photo-tile grid** with
  a header minimum ("Choose 3+") and a sticky bottom CTA that stays disabled until the minimum
  is met.
- **Why needed:** seeds CosFan's primary "follow 3+ creators" onboarding step and cold-start
  personalization.
- **What Claude Design should learn:** header-stated minimum + gated sticky CTA removes "have I
  done enough?" anxiety; selection grid as low-effort interest capture.
- **What NOT to copy:** Spotify's dark theme and dense packing; any read that turns portraits
  into a casting/booking directory. Keep handle + genre labels, zero book/meet/price.

### 2. Home / explore
- **Target filename:** `02-home-explore-sectioned-feed.png`
- **Source app (search in Mobbin):** Depop (iOS) — fallback: Pinterest, YouTube
- **Pattern to capture:** an explore home that leads with a **curated "creators to watch" avatar
  rail**, then a sectioned image-first content grid below; top filter/category chip rail.
- **Why needed:** CosFan explore must feel like fan-membership discovery (people first), not a
  content firehose or a marketplace.
- **What Claude Design should learn:** lead with a *people* rail before content; one feed serves
  many tastes via a top chip rail; airy 2-col image-first browse.
- **What NOT to copy:** ALL marketplace/price/cart/sort-by-price chrome; Pinterest-level density;
  save-to-buy affordances.

### 3. Creator profile
- **Target filename:** `03-creator-profile-membership-entry.png`
- **Source app (search in Mobbin):** Patreon (iOS) — fallback: Instagram creator profile
- **Pattern to capture:** a creator **profile header** (cover + avatar + name + descriptor) with
  a visible **membership/upgrade entry** and a locked-post teaser conveying value; the softest,
  most pastel tonal treatment Patreon offers.
- **Why needed:** this is CosFan's creator profile + membership entry — the conversion surface.
- **What Claude Design should learn:** identity and social proof first, money below the fold;
  free Follow and paid Join can sit as visual peers (open membership, not transactional).
- **What NOT to copy:** "patron/pledge" vocabulary; Patreon orange/coral; exact card
  composition; presence dots or DM/call buttons.

### 4. Membership / paywall
- **Target filename:** `04-membership-tier-paywall.png`
- **Source app (search in Mobbin):** Patreon (iOS)
- **Pattern to capture:** the **subscribe / tier paywall sheet** — price embedded **inside** the
  primary CTA, benefit bullets, a real annual-save callout (or vertical self-contained tier
  cards with per-card Join).
- **Why needed:** CosFan's subscribe sheet / tier comparison — the core monetization screen.
- **What Claude Design should learn:** price-in-CTA + concrete benefits + mathematically-real
  annual save; CTA travels with each option (no select-then-confirm).
- **What NOT to copy:** PPV / per-item "unlock this photo for $X" framing; brand color; fake
  strike-through; per-DM/1:1 tier framing.

### 5. Subscription management
- **Target filename:** `05-subscription-manage-cancel.png`
- **Source app (search in Mobbin):** Netflix (iOS, account/billing) — fallback: Duolingo
  (cancellation flow)
- **Pattern to capture:** the **active-subscription / manage-membership** screen — plain-sentence
  next-billing-date, masked card, **Cancel ↔ Restart as equal options**; or a single honest
  cancel step (one decision, truthful consequence, end-date, easy renew).
- **Why needed:** CosFan's manage-membership and honest-cancel surface — its trust moat.
- **What Claude Design should learn:** state billing facts as plain sentences; keep Cancel one
  tap away and legitimate; one fair decision per screen.
- **What NOT to copy:** Netflix red / dark theme / content-merchandising chrome; any dark pattern
  (hidden cancel, pre-checked resubscribe, guilt maze).

### 6. Message channel
- **Target filename:** `06-message-channel-announcement-feed.png`
- **Source app (search in Mobbin):** Instagram (iOS, broadcast channel) — fallback: Discord
  announcement channel, Cameo update feed
- **Pattern to capture:** a **1:N broadcast channel feed** — every message creator-authored,
  one-tap reaction tallies under each, an honest join/notify gate, **no fan composer**.
- **Why needed:** CosFan's Bubble-style creator→fans channel.
- **What Claude Design should learn:** broadcast-only + reactions is what keeps it 1:N (not a
  fake 1:1 paid chat); an honest join explainer removes spam fear.
- **What NOT to copy:** DMs, presence dots / "Active now", any call/live affordance, two-way
  chat composer for fans.

### 7. Photocard collection
- **Target filename:** `07-photocard-collection-grid.png`
- **Source app (search in Mobbin):** Artsy (iOS, saved artworks) — fallback: Klarna saved items
  (closest pastel white-card surface)
- **Pattern to capture:** a **collection grid** that reads as owned/curated, not a marketplace —
  2-col image grid on white, header count ("N cards"), quiet per-tile provenance captions, save
  toast + friendly empty state.
- **Why needed:** CosFan's photocard collection (OWNED register).
- **What Claude Design should learn:** header count + provenance captions make a collection feel
  owned and motivate completion; white-card-on-white pastel surface.
- **What NOT to copy:** any buy/price/sort/wishlist semantics; Artsy's editorial-serif tone. Use
  OWNED register, never save-to-buy.

### 8. Photocard detail
- **Target filename:** `08-photocard-detail-object.png`
- **Source app (search in Mobbin):** Artsy (iOS, artwork detail) — fallback: Reddit collectible
  avatar detail
- **Pattern to capture:** a **single-object detail** — image-first hero, identity/provenance
  (title/creator/date/edition) **before** any price, Save confirmation.
- **Why needed:** CosFan's single photocard detail — the collectible record.
- **What Claude Design should learn:** image-first + identity/provenance-before-price makes the
  object read as a collectible record, not a buyable asset.
- **What NOT to copy:** buy/bid/inquire/transfer affordances; gallery-commerce chrome; any
  crypto/NFT framing of rarity.

### 9. Event notice
- **Target filename:** `09-event-notice-detail.png`
- **Source app (search in Mobbin):** Eventbrite (iOS, free event detail) — fallback: adidas
  Running structured event, Nextdoor RSVP
- **Pattern to capture:** an **event detail** with "atmosphere → who → when → participate" order
  — hero → organizer row → parsed date/time → free RSVP / add-to-calendar; labeled icon rows for
  density.
- **Why needed:** CosFan's event notice detail.
- **What Claude Design should learn:** parsed date-first; organizer-as-persuader reframes the
  event as a creator broadcast; a single RSVP control is enough for MVP ("announcement, not a
  sale").
- **What NOT to copy:** paid ticketing/checkout, ticket-tier tables; exposed exact address;
  guest-invites-guest chains.

### 10. Safety / report / block
- **Target filename:** `10-report-block-safety-sheet.png`
- **Source app (search in Mobbin):** NGL (iOS, report confirmation + safety resources) —
  fallback: Discord graduated ignore/block, Instagram block confirmation
- **Pattern to capture:** the **post-report confirmation** — success check + reassurance copy +
  inline Block + route to human help; or a **graduated safety sheet** (mute/get-space → block)
  naming the user with honest limits.
- **Why needed:** CosFan's safety surface — the screen that makes the app *feel* safe.
- **What Claude Design should learn:** the post-report screen does the heaviest trust lifting
  (success + reassurance + inline Block + human help); offer graduated options with honest limits.
- **What NOT to copy:** surveillance/policing tone; over-promised enforcement (fake 24/7 "Safety
  Team"); NGL neon / Discord dark theme.

### 11. Settings
- **Target filename:** `11-settings-privacy-subscription.png`
- **Source app (search in Mobbin):** Instagram (iOS, privacy settings hub) — fallback: Gentler
  Streak notification settings, Mimo grouped settings
- **Pattern to capture:** a **grouped settings hub** — iOS grouped lists, sectioned by area
  (privacy, notifications by channel Push vs Email, subscription/billing), plain row labels +
  toggles, marketing default-off and separate from billing alerts.
- **Why needed:** CosFan's settings / privacy / subscription hub.
- **What Claude Design should learn:** calm grouped lists; channel-first then per-type toggles;
  keep marketing default-off and separated from billing.
- **What NOT to copy:** fitness/social-app accent styling; cramming billing and marketing into
  one switch.

### 12. Admin / creator dashboard
- **Target filename:** `12-creator-dashboard-overview.png`
- **Source app (search in Mobbin):** YouTube Studio (iOS, creator dashboard overview) —
  fallback: Spotify for Creators moderation queue, GroupMe manage members
- **Pattern to capture:** an **MVP-light creator/admin overview** — a few headline stat cards +
  a needs-review/moderation list with per-item overflow actions and a destructive confirm
  ("delete + also block" in one step). Keep it light, not a SaaS console.
- **Why needed:** CosFan's MVP creator dashboard / moderation altitude.
- **What Claude Design should learn:** split needs-review vs published; confirm destructive
  actions with stated consequence; combine delete+block.
- **What NOT to copy:** SaaS-console density, dashboards-everywhere creep, analytics overload.

---

## Optional stretch (13–16, capture if time allows)

### 13. Onboarding — screen-one value proposition
- **Target filename:** `13-onboarding-value-prop-intro.png`
- **Source app:** Flo (iOS) — value-proposition intro
- **Pattern to capture:** one headline + exactly **3 benefit rows** (icon + short line) + one CTA;
  generous whitespace, no scroll.
- **Why / learn:** land "Bubble + Patreon + photocard" with one calm value-prop; defer the paywall.
- **What NOT to copy:** health-app imagery; "get closer to her" / deals / crypto wording.

### 14. Lookbook — members-only locked post
- **Target filename:** `14-lookbook-locked-post.png`
- **Source app:** Patreon (iOS) — members-only locked post
- **Pattern to capture:** a real post card (avatar + title + caption snippet) with a **frosted /
  locked media tile**, ONE membership CTA, and a "see N posts" value tally.
- **Why / learn:** show enough metadata to build desire; quantify the unlock; route every locked
  tap to ONE membership join.
- **What NOT to copy (CRITICAL):** "unlock this photo for $X" / tip-to-see; Patreon lock-glyph +
  orange; blur that reads as an adult/PPV teaser. Keep a clean, cute "members only" frosted state.

### 15. Lookbook — unlocked fan post detail
- **Target filename:** `15-lookbook-fan-post-detail.png`
- **Source app:** Weverse (iOS) — fan post detail
- **Pattern to capture:** photo-first creator post → a distinct elevated **"Creator replied"**
  block → threaded fan comments with per-comment like/reply → pinned bottom composer.
- **Why / learn:** manufacture authentic closeness by elevating the creator's **public** reply
  into its own block; per-comment likes for fan-to-fan warmth.
- **What NOT to copy (CRITICAL):** Weverse red chrome; never imply a paid/private 1:1 DM — the
  creator's reply stays a public in-thread comment.

### 16. Message channel — header + member count
- **Target filename:** `16-channel-header-member-count.png`
- **Source app:** Cameo (iOS) — creator→fans update feed
- **Pattern to capture:** the **"<creator> + N fans" channel header** framing 1:N; reaction-primary
  / comment-secondary hierarchy on update cards.
- **Why / learn:** the header frames 1:N membership and trust; reactions primary, comments secondary.
- **What NOT to copy:** "going live / Cameo Call" semantics — layout only.

---

## After capture — flip the readiness verdict

Once the **core 12** are saved in `visual-local/` and the manifest rows are updated, re-run the
readiness check in `VISUAL_EVIDENCE_AUDIT.md`. With local images present for the core groups, the
verdict moves from **NOT READY** to **READY for Claude Design**.
