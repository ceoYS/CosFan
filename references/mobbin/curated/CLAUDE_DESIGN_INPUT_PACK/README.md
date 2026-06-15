# CosFan — Claude Design Input Pack (v0.1)

A curated, design-ready subset of the Mobbin reference collection. **26 references**
selected from 60 raw notes — the minimum set Claude Design needs to design CosFan's
core screens without drowning in raw material.

> **v0.1 change:** added 2 Lookbook / Content refs (13–14) to honor the recommended
> input mix (Lookbook/Content was missing from v0). See `../../AUDIT.md`.

**How to use this pack:** for each CosFan screen group below, read the listed benchmark
notes (paths are relative to this file) and open the Mobbin URLs to study the *pattern*.
Mine the **structure / IA / information order**, then express it in CosFan's own visual
language (below). Do **not** reproduce any source's layout, wording, icons, color, or
brand identity.

> No screenshots are saved (policy). Per-reference visual-inspection briefs live in
> `VISUAL_REFERENCE_MANIFEST.md` — open the Mobbin URL listed there for each screen.
> Full index of all 60 references: `../../MOBBIN_REFERENCE_INDEX.md`
> Raw benchmark notes: `../../raw/<group>/`

---

## CosFan in one paragraph

Mobile-first **B2C fan membership app** for cosplayers, underground idols, photoshoot
models, and subculture creators. Positioning: **Bubble + Patreon + digital photocard** —
fans follow creators, join open memberships, read 1:N creator update channels, and collect
digital photocards. Fan-facing, not a creator SaaS.

### Hard exclusions — CosFan must NOT look like any of these
- adult content / PPV "pay-per-photo" platform
- NFT / crypto / trading-card marketplace
- fake 1:1 paid live chat
- dating / swipe app
- livestream / video-call app
- private meetup / mediation app

If a design decision pushes toward any of the above, it is wrong — choose the safer,
membership-and-collection framing.

---

## Visual system guardrails — "Cool Pastel Collectible OS"

**Do**
- White-first canvas; content (creator photos, photocards) provides the color.
- Pastel accent family: soft blue, mint, lavender, lilac. Used for chips, states, accents — not big fills.
- Clean, practical information density; iOS-native idioms (grouped lists, bottom sheets, chip rails).
- Cute but not childish; collectible but not crypto; fandom warmth that still reads safe.
- Soft rounded cards on white with *restrained* elevation.

**Don't**
- No beige, cream, clay, warm paper, sepia, or muted gold-heavy palettes.
- No glassmorphism, no 3D decorative icons, no excessive/heavy soft shadows.
- No marketplace chrome (price tags, cart, bids, resale), no presence dots / "online now",
  no call/live buttons, no swipe-to-match decks.

**Every reference in this pack is off-palette at source** — transfer the structure, re-skin the look.

---

## The 26 curated references

### Onboarding / Interest (3)
1. **Spotify — pick favorite artists grid** · `../../raw/onboarding/spotify-pick-favorite-artists-grid.md` · https://mobbin.com/flows/2ca9968b-a50d-4910-89e7-e894023d7d21
   *Use for:* CosFan's primary "follow creators" step — photo grid, header minimum ("Pick 3+"), sticky gated CTA. *Avoid:* casting-directory read → keep handle + genre labels, no book/meet/price.
2. **Yahoo News — select 5+ topics grid** · `../../raw/onboarding/yahoo-news-select-5-topics-grid.md` · https://mobbin.com/screens/edd230f6-18a7-4a4a-a8d8-4a6a56ffcb01
   *Use for:* genre/interest multi-select (cosplay series, idol, photoshoot styles) with reassurance microcopy + minimum + sticky CTA.
3. **Flo — value-proposition intro** · `../../raw/onboarding/flo-value-proposition-intro.md` · https://mobbin.com/screens/37b688e4-33a8-4e1c-9350-16214da4cf39
   *Use for:* screen-one positioning — headline + exactly 3 benefit rows + one CTA to land "Bubble + Patreon + photocard". *Avoid:* "get closer to her" / deals / crypto wording.

### Home / Explore (3)
4. **Pinterest — masonry feed + filter chips** · `../../raw/home_explore/pinterest-masonry-feed-with-filter-chips.md` · https://mobbin.com/screens/c41c75fe-19ba-4cc8-837c-91628a3bb493
   *Use for:* calm image-first browse; one feed serves many tastes via a top chip rail. Go airier (2-col + white gutters).
5. **Depop — "creators to watch" rail + grid** · `../../raw/home_explore/depop-sellers-to-watch-then-grid.md` · https://mobbin.com/screens/077eb5df-3011-4a04-baf2-b1818c7ad1f8
   *Use for:* explore that leads with a curated *people* rail before content. *Avoid:* all marketplace/price/cart chrome.
6. **YouTube — home feed + category chips** · `../../raw/home_explore/youtube-home-feed-category-chips.md` · https://mobbin.com/screens/d12ba72a-6af0-4143-9f9c-ac5e5a3cd1bb
   *Use for:* followed-creator home where authorship + one-tap topic chips + inline non-blocking state matter. *Avoid:* video/Shorts chrome.

### Creator Profile (3)
7. **Patreon — pastel profile + upgrade entry** · `../../raw/creator_profile_membership/patreon-pastel-profile-upgrade-entry.md` · https://mobbin.com/flows/fdde05b8-ae13-4cc1-a4b4-1ce14efad3dc
   *Use for:* closest tonal match — creator profile with membership entry + a locked-post teaser conveying value. *Avoid:* "patron/pledge" vocabulary.
8. **Patreon — tier picker (vertical cards)** · `../../raw/creator_profile_membership/patreon-tier-picker-checkout.md` · https://mobbin.com/screens/c4f9b3b6-ea7e-42da-a88c-4dd01690970e
   *Use for:* tier/benefit comparison — vertical self-contained cards (name → price → perks → Join-on-card), no select-then-confirm.
9. **Instagram — creator profile grid** · `../../raw/creator_profile_membership/instagram-creator-profile-grid.md` · https://mobbin.com/screens/55fae9cc-be5b-460c-97f6-1b02e6b07bef
   *Use for:* the profile mental model fans already know — stats triad + visual grid + Follow/Subscribe as visual peers (free + paid).

### Membership / Subscription (3)
10. **Patreon — tier membership paywall** · `../../raw/subscription_billing/patreon-tier-membership-paywall.md` · https://mobbin.com/screens/bb6be2c9-4152-4a0a-8906-71f6770a4ab2
    *Use for:* the subscribe sheet — price inside the CTA, benefit bullets, real annual-save. *Avoid:* PPV per-item framing.
11. **Duolingo — honest cancellation flow** · `../../raw/subscription_billing/duolingo-cancellation-flow.md` · https://mobbin.com/flows/4aeb8ce4-9295-42e4-bc11-13c32c752698
    *Use for:* honest cancel — one decision per screen, truthful consequence, end-date, easy renew. *Avoid:* guilt-maze dark patterns.
12. **Netflix — account billing state** · `../../raw/subscription_billing/netflix-account-billing-state.md` · https://mobbin.com/screens/d903b372-13ed-4905-b2d1-450b2666326d
    *Use for:* transparent active-plan state — plain-sentence renewal date, masked card, Cancel↔Restart as equal options.

### Lookbook / Content (2)
13. **Patreon — members-only locked post** · `../../raw/lookbook_content/patreon-members-only-locked-post.md` · https://mobbin.com/screens/44913b43-97a0-4ced-bfaa-997f5b3337d2
    *Use for:* the locked/conversion state of a lookbook post — frosted thumbnail + visible title/caption + value tally ("see N posts") + ONE membership CTA. *Avoid:* per-photo "$X to unlock" / tip-to-see; adult-PPV teaser blur — keep a clean, cute "members only" frosted state.
14. **Weverse — fan post detail** · `../../raw/lookbook_content/weverse-fan-post-detail.md` · https://mobbin.com/screens/bbc725cf-0014-41d4-8330-91fb9bced4ff
    *Use for:* the unlocked, fandom-native post detail — photo-first post + elevated "Creator replied" block (closeness via authentic public presence) over threaded fan comments. *Avoid:* any implied paid/private 1:1 DM — the creator's reply stays a public in-thread comment.

### Message Channel (2)
15. **Instagram — broadcast channel feed** · `../../raw/message_channel/instagram-broadcast-channel-feed.md` · https://mobbin.com/screens/77621fdc-6426-4763-9ff8-1882eb751de5
    *Use for:* the Bubble-style 1:N channel — read-first feed + reaction tallies + honest join/notify gate. *Avoid:* DMs, presence, calls.
16. **Cameo — creator→fans update feed** · `../../raw/message_channel/cameo-creator-fan-update-feed.md` · https://mobbin.com/screens/c8ba38fd-432c-4cc2-8df9-f99fc04099f8
    *Use for:* "<creator> + N fans" header + reaction-primary / comment-secondary hierarchy. *Avoid:* "going live / Cameo Call" semantics.

### Photocard Collection (3)
17. **Artsy — saved artworks grid** · `../../raw/photocard_collection/artsy-saved-artworks-grid.md` · https://mobbin.com/screens/7e81ec53-2904-4e06-bb1f-4b58ee067b1b
    *Use for:* a collection grid that feels curated and ownership-driven, not a marketplace — header count + provenance captions.
18. **Artsy — artwork detail** · `../../raw/photocard_collection/artsy-artwork-detail.md` · https://mobbin.com/screens/72878c05-7a51-4e00-886f-1bf0a1a09365
    *Use for:* the single photocard/object detail — image-first hero, identity/provenance before any price, Save confirmation. *Avoid:* buy/bid/transfer affordances.
19. **Klarna — saved items grid (surface match)** · `../../raw/photocard_collection/klarna-saved-items-grid.md` · https://mobbin.com/screens/9a2a7793-6ead-4d5d-b370-5d61059450b9
    *Use for:* the exact white-card-on-white pastel surface + save toast + friendly empty state. *Avoid:* wishlist/save-to-buy semantics → use OWNED register.

### Event Notice (3)
20. **Eventbrite — free event detail** · `../../raw/event_notice/eventbrite-free-event-detail.md` · https://mobbin.com/screens/46099065-c93f-42d6-9293-f4f8f9ff9a83
    *Use for:* end-to-end "atmosphere → who → when → participate" anatomy with a no-cost commit. *Avoid:* paid ticketing/checkout.
21. **Nextdoor — community event RSVP** · `../../raw/event_notice/nextdoor-community-event-rsvp.md` · https://mobbin.com/screens/52830538-46ab-4432-9980-9162aa8cd761
    *Use for:* "announcement, not a sale" — free, date-first, simple Going RSVP, honest social proof. *Avoid:* guest-invites-guest / exposed exact address.
22. **adidas Running — structured event detail** · `../../raw/event_notice/adidas-running-structured-event-detail.md` · https://mobbin.com/screens/fdaf7dbf-34d1-4610-89ec-96de84bcbd3d
    *Use for:* information density via labeled icon rows (Date / Time / What / Who-can-attend) + an honest members-only gate.

### Safety / Report / Block (2)
23. **Discord — graduated ignore/block** · `../../raw/safety_report_block/discord-ignore-user-deescalation.md` · https://mobbin.com/screens/0acc46bb-ea2c-46aa-b95e-059671116efc
    *Use for:* non-punitive, graduated safety (mute/get-space → block) with honest limits + escape hatch. *Avoid:* surveillance/policing tone.
24. **NGL — report confirmation + safety resources** · `../../raw/safety_report_block/ngl-report-confirmation-safety-resources.md` · https://mobbin.com/screens/0932f2c5-3f29-4da3-8042-c85170e7f73f
    *Use for:* the post-report screen that makes CosFan *feel* safe — success + reassurance + inline Block + human help. *Avoid:* over-promising enforcement you don't staff.

### My / Settings + Admin / Ops (2)
25. **Gentler Streak — notification settings (Push/Email)** · `../../raw/my_settings/gentler-streak-notification-settings-push-email.md` · https://mobbin.com/screens/33a9da03-3400-445d-9e4e-943e33d1f2de
    *Use for:* calm settings — channel-first (Push vs Email) then per-type toggles, inline email, marketing default-off and separate from billing alerts.
26. **Spotify for Creators — moderation queue** · `../../raw/admin_ops/spotify-for-creators-comment-moderation-queue.md` · https://mobbin.com/screens/db770b06-a394-4ba3-95ab-db5183c8d997
    *Use for:* MVP-light admin altitude — needs-review tabs + per-item overflow actions + destructive confirm ("delete + also block"). *Avoid:* SaaS-console creep.

---

## Cross-cutting principles (distilled from all 26)

1. **Defer money below the fold.** Identity and social proof first; price/CTA one tap deeper. (Profiles, paywall, events.)
2. **Free + paid as visual peers.** Follow (free) and Join/Subscribe (paid) sit side by side — CosFan is *open membership*, never transactional access.
3. **Membership layer, never per-item.** Locked content unlocks via *one* membership join, with a value tally ("see N posts") — never PPV "pay for this photo".
4. **Honesty as a feature.** Price-in-CTA, plain renewal dates, one-tap cancel, "remind me before renewal", transparent report pipeline. Honesty is CosFan's trust moat against the "adult/scam" read.
5. **Broadcast, not chat.** The channel is 1:N creator→fans with reactions; no DMs, presence, or calls.
6. **Owned, not traded.** Photocards live in the OWNED register (collection, provenance, rarity-as-history) — never price, bids, resale, or transfer.
7. **Closeness via presence, not paid DMs.** Elevate the creator's own *public* reply ("Creator replied") to manufacture authentic closeness — never a fake paid 1:1 chat.
8. **Safe by construction.** Graduated safety tools, fandom-specific report taxonomy (incl. "sexual/explicit", "leaked paid content"), reassurance after every report.
9. **Calm density.** iOS grouped lists, chip rails, bottom sheets; airy 2-col pastel; content carries the color.

## Design from scratch — no clean Mobbin precedent
- A pastel/collectible, cosplay-native visual expression across every screen (this is CosFan's differentiation).
- A true "owned digital photocard from a creator" with edition framing **minus** commerce — compose from refs 17 + 18 + 19 plus non-crypto rarity/provenance (`../../raw/photocard_collection/reddit-collectible-avatar-detail.md`).
- A wholesome-B2C Community Guidelines / Safety Center surface (no strong exemplar found).
