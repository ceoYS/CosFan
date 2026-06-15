# CosFan — Mobbin Reference Index (v0)

Pattern-mining index for CosFan design. Grouped by CosFan screen group.
References are **pattern benchmarks**, not designs to copy. Every entry points to a
local benchmark note in `raw/<group>/` and a canonical Mobbin URL. Several notes
triangulate a pattern across 2–4 related screens, so the index shows **one canonical
link per note (60 links)** while the notes cite **87 Mobbin screens** in total.

- **Source:** Mobbin MCP (authenticated), platform = iOS, mobile-first.
- **Collected:** 2026-06-15 · 60 benchmark notes across 11 groups.
- **What is NOT here:** no screenshots saved/committed (notes + URL pointers only);
  no NFT/crypto, voice/video/live-call, dating-swipe, adult/PPV, or trading-marketplace
  references (explicitly discarded during collection).

**Global guardrail for every reference below:** the *structure/IA* transfers, the
*visual expression does not*. All sources are off-palette and must be re-skinned to
**Cool Pastel Collectible OS** — white-first, pastel blue/mint/lavender/lilac, clean
density, cute-not-childish, collectible-not-NFT. No beige/cream/clay/sepia, no
glassmorphism, no 3D decorative icons, no heavy soft shadows.

Legend: ⭐ = selected for the Claude Design input pack (see
`curated/CLAUDE_DESIGN_INPUT_PACK/README.md`).

---

## 1. Onboarding

**Recommended source apps:** Spotify (follow-artists grid), Yahoo News / X (interest chips),
Duolingo (one-question wizard + push priming), Flo (value-prop), Clubhouse (pre-checked follow).

**Collected references**
- ⭐ `raw/onboarding/spotify-pick-favorite-artists-grid.md` — Spotify "Choose 3+ artists" photo grid — https://mobbin.com/flows/2ca9968b-a50d-4910-89e7-e894023d7d21
- ⭐ `raw/onboarding/yahoo-news-select-5-topics-grid.md` — Yahoo News "Select 5+ topics" chip grid — https://mobbin.com/screens/edd230f6-18a7-4a4a-a8d8-4a6a56ffcb01
- ⭐ `raw/onboarding/flo-value-proposition-intro.md` — Flo welcome value-prop (headline + 3 benefits + CTA) — https://mobbin.com/screens/37b688e4-33a8-4e1c-9350-16214da4cf39
- `raw/onboarding/clubhouse-follow-people-you-know-grid.md` — Clubhouse pre-checked follow grid + bulk accept — https://mobbin.com/screens/0cd92c58-31d8-4f42-be4e-35b4128e9373
- `raw/onboarding/duolingo-goal-single-select-steps.md` — Duolingo one-question-per-screen wizard — https://mobbin.com/flows/b0b4f93f-5637-46ec-9d77-49ecda6b991d
- `raw/onboarding/duolingo-notification-priming-benefit.md` — benefit-first push priming before OS dialog — https://mobbin.com/screens/94253387-59a2-4616-8a7a-9a4001a159cc

**Key UX lessons**
- State the minimum in the header ("Pick 3+ creators / 5+ genres") and gate Continue on it — kills "have I done enough?" anxiety and seeds cold-start personalization.
- Bind interest to *people*: circular avatar + handle + genre label + search; pre-seed so the grid is never empty.
- Reassurance microcopy ("you'll still discover new creators, change anytime") defuses over-commitment.
- Run benefit-first notification priming AFTER creator selection so copy is personalized ("never miss a drop"); quiet "Maybe later"; OS prompt only on Enable.
- Open with one value-prop screen (headline + exactly 3 benefit rows + one CTA); keep preference questions ≤3, one-per-screen; defer paywall until after investment.

**Risks to avoid**
- Glossy portrait grids can read as a casting/model directory — keep handle+genre labels, zero "book/meet/price" affordances.
- Value-prop & push copy is where positioning leaks — steer to fandom/collecting/supporting, never "get closer to her", deals, or crypto.

**MVP action:** Spotify-style follow-creators grid + Yahoo-style genre chips with header minimum and sticky CTA → personalized push-priming → Flo-style one-screen value prop. Re-skin all to pastel.

**In Claude Design pack:** Yes — 3 (Spotify, Yahoo News, Flo).

---

## 2. Home / Explore

**Recommended source apps:** Pinterest (masonry + category browse), Depop (creators-to-watch rail), Instagram (explore grid), YouTube (category chips home).

**Collected references**
- ⭐ `raw/home_explore/pinterest-masonry-feed-with-filter-chips.md` — Pinterest masonry feed + top filter chips — https://mobbin.com/screens/c41c75fe-19ba-4cc8-837c-91628a3bb493
- ⭐ `raw/home_explore/depop-sellers-to-watch-then-grid.md` — "Sellers to watch" people rail above content grid — https://mobbin.com/screens/077eb5df-3011-4a04-baf2-b1818c7ad1f8
- ⭐ `raw/home_explore/youtube-home-feed-category-chips.md` — followed-creator home, sticky category chips + authored cards — https://mobbin.com/screens/d12ba72a-6af0-4143-9f9c-ac5e5a3cd1bb
- `raw/home_explore/pinterest-category-browse-sectioned.md` — search + sectioned category browse "doors" — https://mobbin.com/screens/205983bb-dce1-41c3-b1a2-90972d90e13b
- `raw/home_explore/instagram-explore-discovery-grid.md` — 3-col discovery grid w/ facet tabs — https://mobbin.com/screens/43a5a9b0-f63e-4521-968a-05b28dca770c
- `raw/home_explore/depop-explore-home-sectioned-with-categories.md` — Explore: mode tabs + fresh grid + "Browse categories" fallback — https://mobbin.com/screens/5d28da42-cb06-4af9-ac97-238569809e11

**Key UX lessons**
- Lead with imagery, minimal chrome; a top chip rail lets one feed serve many tastes.
- Bind every browse tile to a creator (avatar + name) so follow/subscribe is one tap from the graze — keeps explore feeling like fan-membership, not a stock-photo wall.
- Lead discovery with a curated *people* rail ("Creators to watch") before the content firehose; editorial section titles imply curation = trust.
- Explore / For-you / Following tab triad separates intents; pair algorithmic feed with a "Browse by category" fallback.

**Risks to avoid**
- Discard marketplace-checkout chrome (price tags, cart, sort-by-price) and full-screen vertical-video/Shorts framing.
- Algorithmic "For you" + auto-pulled covers can surface suggestive content — require safety curation + hand-curated covers.
- Lean airier than Pinterest/IG density: 2-col pastel with white gutters (collectible-not-cluttered).

**MVP action:** Followed-creator home (YouTube chips model) + Explore with creators-to-watch rail (Depop) over a calm masonry/2-col grid (Pinterest). Strip all commerce; hand-curate covers.

**In Claude Design pack:** Yes — 3 (Pinterest masonry, Depop creators-to-watch, YouTube chips).

---

## 3. Creator Profile / Membership

**Recommended source apps:** Patreon (profile + tier picker), Instagram (profile grid), Substack (subscribe pair), Depop (trust cluster).

**Collected references**
- ⭐ `raw/creator_profile_membership/patreon-pastel-profile-upgrade-entry.md` — pastel creator profile (Worlds Beyond Number) + "Upgrade membership" + locked post — https://mobbin.com/flows/fdde05b8-ae13-4cc1-a4b4-1ce14efad3dc
- ⭐ `raw/creator_profile_membership/patreon-tier-picker-checkout.md` — stacked tier cards + price + per-card Join + custom pledge — https://mobbin.com/screens/c4f9b3b6-ea7e-42da-a88c-4dd01690970e
- ⭐ `raw/creator_profile_membership/instagram-creator-profile-grid.md` — profile stats triad + grid + Follow/Subscribe peers — https://mobbin.com/screens/55fae9cc-be5b-460c-97f6-1b02e6b07bef
- `raw/creator_profile_membership/patreon-creator-profile-conversion-entry.md` — profile w/ "Join for free" + membership entry — https://mobbin.com/screens/c02c76d2-255f-433b-9a63-0e9e463bc336
- `raw/creator_profile_membership/substack-writer-profile-subscribe.md` — Subscribe(paid)+Follow(free) pair + post list — https://mobbin.com/screens/462ce8d8-8a2d-40fc-8579-ac9ba9b18b03
- `raw/creator_profile_membership/depop-seller-profile-trust-grid.md` — trust badge cluster + Reviews tab + grid — https://mobbin.com/screens/9125618d-6ce3-45d9-9977-27bd9c660492

**Key UX lessons**
- Lead profile with identity + social proof (name, one-line descriptor, member/follower counts); defer price one tap deeper — header calm, money below the fold.
- Two-action relationship: free Follow and paid Join/Subscribe as visual peers (IG, Substack) — best fit for "open fan membership, not transactional".
- Tier comparison = vertical stack of self-contained cards (name → price → perks → Join-on-card), thumb-friendly, no select-then-confirm step.
- Make paywall reward concrete: members-only posts as locked cards with visible title + thumbnail + lock chip; non-members see what they'd unlock without a hard wall.
- De-risk lesser-known creators with a soft trust layer (active recently, member counts, optional testimonials) — adapt from Depop, drop literal 5-star "rate a person".

**Risks to avoid**
- No PPV/per-content unlock framing; locked content = open membership, never per-post pricing.
- Steer tier copy to ongoing perks (early access, exclusive posts, photocards), never per-DM/1:1 paid-chat access.
- Drop Patreon "patron/pledge" vocabulary → "membership / tier / perks".

**MVP action:** IG-style profile header + grid with Follow/Join as peers → Patreon vertical tier cards on tap → locked-post teaser to convey value. Re-skin to pastel.

**In Claude Design pack:** Yes — 3 (Patreon pastel profile, Patreon tier picker, IG profile grid).

---

## 4. Subscription / Billing

**Recommended source apps:** Patreon (membership paywall), Duolingo (plan picker + honest cancel), Netflix (billing state + manage), Calm (trial renewal reminder).

**Collected references**
- ⭐ `raw/subscription_billing/patreon-tier-membership-paywall.md` — tier paywall, price-in-CTA + benefit bullets + annual-save — https://mobbin.com/screens/bb6be2c9-4152-4a0a-8906-71f6770a4ab2
- ⭐ `raw/subscription_billing/duolingo-cancellation-flow.md` — honest cancel (reason survey, honest consequence, end-date, easy renew) — https://mobbin.com/flows/4aeb8ce4-9295-42e4-bc11-13c32c752698
- ⭐ `raw/subscription_billing/netflix-account-billing-state.md` — active-plan + billing state (plain renewal date, masked card, Cancel↔Restart) — https://mobbin.com/screens/d903b372-13ed-4905-b2d1-450b2666326d
- `raw/subscription_billing/duolingo-plan-selection-annual-vs-monthly.md` — plan picker, per-month normalization, "Cancel anytime" — https://mobbin.com/screens/ac6f6af9-c6c9-455e-817e-a3a4b18d36f7
- `raw/subscription_billing/netflix-manage-membership-change-plan.md` — manage hub, effective-date-first, Change/Pause/Cancel equal — https://mobbin.com/screens/34847475-864a-44f0-b773-95e6b99b4b77
- `raw/subscription_billing/calm-paywall-honest-renewal-reminder.md` — trial paywall, terms-in-eyeline + "remind me before renewal" toggle — https://mobbin.com/screens/4c9d15dc-9785-4a9b-8c1f-64a17d5c1e27

**Key UX lessons**
- Embed exact price/commitment in the primary CTA ("Start membership — $X/mo"); normalize plans to per-month so comparison needs no math.
- State billing facts as plain sentences in one eyeline ("Your next billing date is 16 April", masked card) — not buried fine print.
- Keep Cancel one tap away, framed as a legitimate equal option; after cancel show status banner + access-end date + easy Resume.
- Honest retention = ONE fair trade-off or a genuine Pause — never a multi-screen guilt maze.
- A "remind me before trial/renewal ends" toggle is the best anti-surprise-charge affordance — adopt verbatim.

**Risks to avoid**
- No PPV "pay to see this one photo"; recurring membership value only.
- No dark-pattern cancellation (hidden cancel, pre-checked re-subscribe, "call to cancel").
- Savings/strike-through must be mathematically real for CosFan's actual prices.

**MVP action:** Patreon-style membership sheet (price-in-CTA) → Netflix-style transparent billing state → Duolingo-style honest cancel + Calm renewal reminder.

**In Claude Design pack:** Yes — 3 (Patreon paywall, Duolingo cancel, Netflix billing state).

---

## 5. Lookbook / Content

**Recommended source apps:** Instagram (post detail + comments sheet), Patreon (member post + locked post), Substack (article detail), Weverse (idol→fan post tone).

**Collected references**
- ⭐ `raw/lookbook_content/patreon-members-only-locked-post.md` — members-only locked post (lock on media + "unlock N posts" tally) — https://mobbin.com/screens/44913b43-97a0-4ced-bfaa-997f5b3337d2
- ⭐ `raw/lookbook_content/weverse-fan-post-detail.md` — idol/creator→fan post + "Artist's comments" block — https://mobbin.com/screens/bbc725cf-0014-41d4-8330-91fb9bced4ff
- `raw/lookbook_content/instagram-single-post-detail.md` — clean photo-first post detail + reactions + comments — https://mobbin.com/screens/2d659583-39e3-49eb-a376-9610fcb97024
- `raw/lookbook_content/patreon-member-post-detail.md` — unlocked member post (zero purchase chrome) — https://mobbin.com/screens/4506758a-2b7a-45ee-a16d-5a43aebcffa5
- `raw/lookbook_content/substack-article-post-detail.md` — article detail (title + body + inline captioned image) — https://mobbin.com/screens/67ffc0f8-88ee-4185-b071-2bc4ebe19ffa
- `raw/lookbook_content/instagram-comments-bottom-sheet.md` — threaded comments sheet + per-comment like + emoji bar — https://mobbin.com/screens/f5db6252-33d7-478a-a442-6e0f9f3987d1

**Key UX lessons**
- Media is the product: full-bleed photo, lowest-effort reaction first, comments deferred.
- Resolve access at the MEMBERSHIP layer, not per-item: an unlocked members post carries zero purchase chrome ("you're in, here's the drop").
- For locked content show metadata + frosted thumbnail + quantified unlock ("see N posts"), route every locked tap to ONE membership join.
- Elevate the creator's own public reply into a labeled block ("Artist's comments") — presence, not paid DMs.
- Bottom-sheet comments that retain post context + cute quick-emoji + per-comment like = cheap, frequent fan affection.

**Risks to avoid**
- No PPV "unlock this photo for $X" / tip-to-see; locked = membership belonging.
- Locked thumbnail = clean frosted "members only", not adult/PPV teaser blur.
- "Creator replied / closeness" must be public in-thread, never a fake paid 1:1 chat.

**MVP action:** IG photo-first post detail (accessible posts) + Patreon locked-post state (membership value) + Weverse-style labeled creator reply. Strip all per-item commerce.

**In Claude Design pack:** Yes — 2 (Patreon members-only locked post, Weverse fan post detail). *Promoted in v0.1 to honor the recommended input mix (Lookbook/Content was missing from v0); see `AUDIT.md`.*

---

## 6. Message Channel

**Recommended source apps:** Instagram (broadcast channels), Cameo (creator→fans update feed), WhatsApp Channels (follow/discovery), Discord (read-only announcement).

**Collected references**
- ⭐ `raw/message_channel/instagram-broadcast-channel-feed.md` — broadcast channel feed (join/notify gate + reactions) — https://mobbin.com/screens/77621fdc-6426-4763-9ff8-1882eb751de5
- ⭐ `raw/message_channel/cameo-creator-fan-update-feed.md` — "<creator> + N fans" update feed, reaction-primary/comment-secondary — https://mobbin.com/screens/c8ba38fd-432c-4cc2-8df9-f99fc04099f8
- `raw/message_channel/instagram-creator-broadcast-reactions-poll.md` — verified creator broadcast + inline poll + Report/Leave — https://mobbin.com/screens/fa02d76c-7571-40a2-b764-80b0597f8389
- `raw/message_channel/whatsapp-channels-follow-discovery.md` — follow/discovery model for channels — https://mobbin.com/screens/31d72e23-5de9-4789-8674-0d4d00d5a060
- `raw/message_channel/discord-announcement-channel-readonly.md` — read-only announcement/broadcast channel — https://mobbin.com/screens/62650df9-70fb-47fd-bdbe-322b95a7ee37

**Key UX lessons**
- Broadcast-only by default: every message creator-authored; fans engage via one-tap reactions (comments secondary). This is what keeps it 1:N, not a fake 1:1 paid chat.
- Honest join/notification explainer ("added to your inbox, you'll get notifications") removes commitment/spam fear.
- Header = creator identity + member count + verified badge → frames 1:N + trust, at top.
- Inline poll/quick-question cards = high-value, low-friction participation beyond reactions.
- Pinned "start here" post + "new since last visit" marker keep a read-only feed alive.

**Risks to avoid (enforced during collection)**
- Excluded all voice channels, video/live, "join call", screen-share, and online-presence (green dots / "Active now"). CosFan channel stays asynchronous, no presence, no call.
- Cameo "Cameo Call / going live" semantics stripped — layout only.

**MVP action:** IG-style broadcast channel (read-first feed + reactions + honest join gate) branded as creator→fans, plus inline polls. No DMs, no presence, no calls.

**In Claude Design pack:** Yes — 2 (IG broadcast channel, Cameo update feed).

---

## 7. Photocard Collection

**Recommended source apps:** Artsy (artwork detail + saved grid), Klarna (saved grid surface), Instagram (saved collections), Reddit (non-NFT collectible rarity/provenance), Pinterest (boards).

**Collected references**
- ⭐ `raw/photocard_collection/artsy-saved-artworks-grid.md` — "Saved Artworks" 2-col collection grid — https://mobbin.com/screens/7e81ec53-2904-4e06-bb1f-4b58ee067b1b
- ⭐ `raw/photocard_collection/artsy-artwork-detail.md` — single artwork detail (title/artist/year/medium + Save) — https://mobbin.com/screens/72878c05-7a51-4e00-886f-1bf0a1a09365
- ⭐ `raw/photocard_collection/klarna-saved-items-grid.md` — white-card grid + save toast + empty state (pastel surface match) — https://mobbin.com/screens/9a2a7793-6ead-4d5d-b370-5d61059450b9
- `raw/photocard_collection/instagram-saved-collections.md` — saved collections (mosaic covers + count + private lock) — https://mobbin.com/screens/ab39bbed-891a-4e65-a58d-4258c667af1d
- `raw/photocard_collection/reddit-collectible-avatar-detail.md` — collectible detail with rarity tier + provenance (NON-NFT) — https://mobbin.com/screens/88b939e1-75ea-4216-90a8-7aadf4046f14
- `raw/photocard_collection/pinterest-saved-boards.md` — catch-all bucket + recency + sections — https://mobbin.com/screens/3a7456a3-4ce5-49f6-80dc-533c7326dd51

**Key UX lessons**
- Image-first, identity/provenance-before-price (Artsy detail) makes a single object read as a refined collectible record, not a paywall or buyable asset.
- A header count ("N cards") + quiet per-tile provenance captions makes a collection feel owned and motivates completion, no marketplace pressure.
- White rounded-card-on-white + per-tile creator avatar chip (Klarna) = the exact Cool Pastel Collectible OS surface; pair with save toast + friendly empty state.
- Rarity/scarcity without crypto (Reddit): rarity-tier panel + provenance line ("from [creator]'s drop, [date]") = personal earned history, not price/tradeability.
- Save first, organize later: auto catch-all bucket + auto-grouping into per-creator sets with mosaic covers + private-lock glyph.

**Risks to avoid (enforced during collection)**
- Discarded ALL NFT/crypto/marketplace detail screens surfaced (Rarible, OpenSea, Family/Parallel, Fanatics Live trading cards). No price/bids/resale/transfer/"Send" affordances; OWNED register only ("your collection"), never wishlist/save-to-buy.

**MVP action:** Artsy-style collection grid + object detail (image-first, provenance not price) on Klarna's white-card pastel surface; Reddit-style non-crypto rarity/provenance line; IG/Pinterest auto-grouping for scale.

**In Claude Design pack:** Yes — 3 (Artsy grid, Artsy detail, Klarna grid).

---

## 8. Event Notice

**Recommended source apps:** Eventbrite (free event detail + location block), Nextdoor (community RSVP), adidas Running (structured labeled rows + gate), Saturn (event anatomy), Luma (events list).

**Collected references**
- ⭐ `raw/event_notice/eventbrite-free-event-detail.md` — free event detail (hero + organizer + parsed date + add-to-calendar) — https://mobbin.com/screens/46099065-c93f-42d6-9293-f4f8f9ff9a83
- ⭐ `raw/event_notice/nextdoor-community-event-rsvp.md` — community event (FREE, "Going" RSVP dropdown, honest attendance) — https://mobbin.com/screens/52830538-46ab-4432-9980-9162aa8cd761
- ⭐ `raw/event_notice/adidas-running-structured-event-detail.md` — labeled Date/Time/Type icon rows + explained gate — https://mobbin.com/screens/fdaf7dbf-34d1-4610-89ec-96de84bcbd3d
- `raw/event_notice/luma-your-events-list.md` — events list (date-rail chips + thumbnails + Going/Hosting pills) — https://mobbin.com/screens/8b8267f0-7fd4-4c93-8455-70be3ae9ede5
- `raw/event_notice/eventbrite-location-map-block.md` — About + Location block (map, address, transit) — https://mobbin.com/screens/33c3642c-5be8-4d1e-a678-0e965f3167a3
- `raw/event_notice/saturn-event-detail-anatomy.md` — compact event anatomy (date/repeat/location/host/visibility) — https://mobbin.com/screens/ddf86d6f-f33b-469f-9739-04043ea44b74

**Key UX lessons**
- Lead with parsed date/time, not prose — answer "when" before any scroll.
- Make the creator the persuader, high on the page: organizer row + avatar + name + Follow = trust anchor, reframes event as creator broadcast.
- A single RSVP control is enough — Going/Interested/Not + Add-to-calendar; no ticketing needed for MVP.
- Labeled icon rows (Date / Time / What / Who-can-attend) maximize information density and scannability.
- Location = map + written address + directions, with explicit "Online" and "revealed to attendees" states for safety.

**Risks to avoid**
- Do NOT model paid ticketing/checkout (out of MVP scope) — capture info density, not purchase.
- Private-meetup / dating-meet risk: events are PUBLIC creator broadcasts; gate/abstract exact addresses; no guest-invites-guest chains.

**MVP action:** Eventbrite-style date-first detail anatomy + Nextdoor free RSVP + adidas labeled rows + safe location states. Keep monetization quiet/secondary.

**In Claude Design pack:** Yes — 3 (Eventbrite free detail, Nextdoor RSVP, adidas structured rows).

---

## 9. Safety / Report / Block

**Recommended source apps:** Discord (graduated ignore/block), NGL (report confirmation + resources), Instagram (block confirmation), Threads (report-status timeline), Nextdoor (reason taxonomy), YouTube (reassurance).

**Collected references**
- ⭐ `raw/safety_report_block/discord-ignore-user-deescalation.md` — graduated "Ignore <user>?" de-escalation (mute→block, honest limits) — https://mobbin.com/screens/0acc46bb-ea2c-46aa-b95e-059671116efc
- ⭐ `raw/safety_report_block/ngl-report-confirmation-safety-resources.md` — "Message reported" confirmation + inline Block + safety resources — https://mobbin.com/screens/0932f2c5-3f29-4da3-8042-c85170e7f73f
- `raw/safety_report_block/instagram-block-user-confirmation.md` — block confirmation sheet (answers the 3 fears) — https://mobbin.com/screens/8d7af7e3-3c9f-4aa6-afb8-d64665c8fa06
- `raw/safety_report_block/threads-report-status-timeline.md` — report-status 3-step timeline (Received→Review→Resolved) — https://mobbin.com/screens/a292f19e-5d94-4ff2-802e-53025c2c608c
- `raw/safety_report_block/nextdoor-report-reason-taxonomy.md` — reason taxonomy + "Thanks for your report" + Undo — https://mobbin.com/screens/46d281f3-43ac-4451-add6-62b4509e7b7b
- `raw/safety_report_block/youtube-report-community-reassurance.md` — "Thanks for helping our community" reassurance — https://mobbin.com/screens/5a673452-f483-4f67-b317-fbdd3a0bdf26

**Key UX lessons**
- Block = ONE sheet naming WHO + answering three fears: they lose access, they won't be notified, you can undo. "Won't be notified" is the highest-value line, placed where users hesitate.
- Offer a graduated model — light "Mute/Get space" → hard "Block" — with honest limits, so anxious users still set a boundary.
- Post-report confirmation does the heaviest trust lifting: success check + reassurance + one-tap Block + route to human help/guidelines.
- Show moderation as a transparent pipeline (Received → Under review → Resolved) to kill the "black hole" fear.
- Frame reporting as pro-social care; plain-language reasons with "Something else" last + optional note; always Undo; include an "immediate danger → emergency services" line.

**Risks to avoid**
- Don't over-promise enforcement (no fake 24/7 "Safety Team", guaranteed removal) beyond what CosFan staffs.
- Avoid punitive/surveillance framing → supportive "get space / helping our community".
- Replace Nextdoor's local-politics taxonomy with a fandom-safety set incl. "sexual/explicit content" and "leaked paid content" (reinforces anti-PPV/anti-meetup positioning).

**MVP action:** Discord graduated mute→block + IG block confirmation (3 fears) + NGL post-report reassurance + Threads status timeline; fandom-specific reason taxonomy.

**In Claude Design pack:** Yes — 2 (Discord de-escalation, NGL report confirmation).

---

## 10. My / Settings

**Recommended source apps:** Mimo (grouped hub + Danger zone), Gentler Streak (channel-first notification toggles), Instagram (privacy hub). *(Coffee Meets Bagel borrowed for list STRUCTURE only — dating semantics stripped.)*

**Collected references**
- ⭐ `raw/my_settings/gentler-streak-notification-settings-push-email.md` — Push/Email grouped notification toggles (+ inline email) — https://mobbin.com/screens/33a9da03-3400-445d-9e4e-943e33d1f2de
- `raw/my_settings/mimo-grouped-settings-hub.md` — grouped settings hub w/ isolated "Danger zone" — https://mobbin.com/screens/bfee415b-e542-45e9-bb43-01735b0074d9
- `raw/my_settings/instagram-privacy-settings-hub.md` — privacy hub grouped by intent (visibility + interaction) — https://mobbin.com/screens/0f9d4587-5ce2-4d93-b1b2-0f9492afb50f
- `raw/my_settings/coffee-meets-bagel-account-settings-with-toggles.md` — account group + per-type push toggles (STRUCTURE ONLY) — https://mobbin.com/screens/a0dea3ec-9b34-4539-b58a-afce05c15507

**Key UX lessons**
- iOS grouped-list idiom: group by intent with plain headers, low-stakes changes inline, destructive actions isolated in a "Danger zone".
- Notifications two-axis: channel (Push vs Email) then per-type; show email destination inline; marketing as one clearly-labeled, default-off switch separate from billing alerts.
- Privacy reads best as questions ("Who can see my page") with current state inline and safety tools (block/restrict/hidden words) co-located; zero monetization.

**Risks to avoid**
- Dating-category bleed (Coffee Meets Bagel) — structure only, strip likes/incognito/matchmaking.
- "Manage membership" stays a neutral utility row, not a paywall nag.

**MVP action:** Mimo-style grouped hub + Gentler Streak two-axis notifications + IG-style privacy questions with safety tools co-located.

**In Claude Design pack:** Yes — 1 (Gentler Streak notifications).

---

## 11. Admin / Ops

**Recommended source apps:** YouTube Studio (lightweight creator overview), Spotify for Creators (mobile moderation queue), GroupMe (member management).

**Collected references**
- ⭐ `raw/admin_ops/spotify-for-creators-comment-moderation-queue.md` — mobile moderation queue (needs-review tabs + delete/block confirm) — https://mobbin.com/screens/db770b06-a394-4ba3-95ab-db5183c8d997
- `raw/admin_ops/youtube-studio-creator-dashboard-overview.md` — creator dashboard overview w/ KPI cards — https://mobbin.com/screens/4ee1a553-bbfb-4d6b-818e-5deedc455ab2
- `raw/admin_ops/groupme-manage-members-roles-remove.md` — member management (role groups + overflow remove/report) — https://mobbin.com/screens/4a2434e9-8de0-4f70-8d03-0d9ef11f3097

**Key UX lessons**
- Lightweight creator admin = glanceable overview, not a SaaS console: one headline KPI (members), 2-3 stat cards, recent content with inline metrics, tools in a bottom tab bar, legible zero-state.
- Mobile moderation: split needs-review vs published, actions via per-item overflow sheet, confirm destructive actions with stated consequence, combine "delete + also block" in one step.

**Risks to avoid**
- SaaS-console creep — cap KPIs at 2-3; admin is MVP-light (members/content/notices + basic stats).
- Removing a paying member / deleting accounts must route through confirms and handle subscription/billing state.

**MVP action:** YouTube-Studio-altitude overview + Spotify-for-Creators moderation queue + GroupMe member management. Keep minimal; fan-facing B2C, not a creator SaaS.

**In Claude Design pack:** Yes — 1 (Spotify for Creators moderation queue).

---

## Coverage summary

| # | Group | Notes | In design pack |
|---|-------|-------|----------------|
| 1 | Onboarding | 6 | 3 |
| 2 | Home / Explore | 6 | 3 |
| 3 | Creator Profile / Membership | 6 | 3 |
| 4 | Subscription / Billing | 6 | 3 |
| 5 | Lookbook / Content | 6 | 2 |
| 6 | Message Channel | 5 | 2 |
| 7 | Photocard Collection | 6 | 3 |
| 8 | Event Notice | 6 | 3 |
| 9 | Safety / Report / Block | 6 | 2 |
| 10 | My / Settings | 4 | 1 |
| 11 | Admin / Ops | 3 | 1 |
| | **Total** | **60** | **26** |

**Known gaps (design from first principles — no clean precedent on Mobbin):**
- No pastel/collectible, cosplay-native onboarding, profile, channel, or photocard exemplar — CosFan's visual expression is its differentiation, must be designed not benchmarked.
- No true "owned digital photocard from a creator with edition framing, minus commerce" — compose from Artsy (detail/grid) + Reddit (rarity/provenance) + Klarna (surface).
- No strong wholesome-B2C "Community Guidelines / Safety Center" exemplar (results skewed dating/legal-lists) — structural hints only.
- No in-app card-entry / payment-method screen (apps defer to App Store) — out of MVP scope anyway.
