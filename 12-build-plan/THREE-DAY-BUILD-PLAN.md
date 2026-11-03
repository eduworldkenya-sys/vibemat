# VibeMat Three-Day Build Sprint

**Decision date:** 2026-11-03  
**Owner direction:** Build VibeMat in a focused three-day sprint: frontend on Day 1, backend on Day 2, integration and product completion on Day 3.  
**Product identity:** VibeMat — As We Move. / Everyone Moves.  
**Product definition:** A mobile-first social media network for transport and the wider movement ecosystem.  
**Status:** Owner-approved delivery target and working plan; not a claim that the product is already implemented or that production readiness can be guaranteed in three days.

## 1. Why a three-day sprint is the chosen approach

VibeMat is not inventing social networking, maps, video delivery, messaging, storage, or push notifications. These are established capabilities. The build should compose managed services and mature libraries, while concentrating custom engineering on VibeMat's product logic:

- Social discovery connected to places, routes, stages, vehicles, businesses, and movement.
- A hybrid experience combining social feed and mobility intelligence.
- Global discovery with local relevance and user-selected place following.
- Evidence-aware transport updates and incident distribution.
- One connected network for ordinary people, creators, transport participants, and businesses.

Do not build proprietary video infrastructure, a map engine, a messaging protocol, or a new notification delivery network for the first pilot.

## 2. Delivery target and honest completion standard

The three-day target is a **working pilot build**, not a promise of global-scale capacity, mature recommendation science, fully automated emergency response, or production certification.

A feature is complete only when its real user journey works against persisted backend data and appropriate permissions. A visual screen, mock response, seeded-only demonstration, or clickable placeholder is not a completed feature.

If a third-party credential, approval, provider account, or device permission is unavailable, record the blocker and provide an honest degraded state. Never display fabricated live data or claim a notification, upload, booking, dispatch, or payment succeeded when it did not.

## 3. Three-day sequence

### Day 1 — Frontend experience (2026-11-03)

Build the mobile-first product shell and core screens with realistic loading, empty, error, and permission states.

Required surfaces:

1. **Home:** hybrid social feed with access to mobility intelligence / Pulse.
2. **Explore:** search and map, with place, route, corridor, stage, and nearby discovery entry points.
3. **Create:** short video, photo, text, and movement/road update entry points.
4. **Communities:** discover, follow, and view community discussions.
5. **Profile:** personal profile, creator content, optional business/provider profile entry points, follows, and settings.
6. **Content viewer:** vertical short-video experience with author, caption, location/context, follow, like, comment, share, and save affordances.
7. **Pulse / incidents:** incident and road update cards with source, time, status, and freshness labels.
8. **Transport discovery:** provider/business listings and independent boda/taxi/provider profile presentation.
9. **Messaging:** basic inbox and conversation screens.
10. **Notification centre:** grouped activity and meaningful incident alerts.

Frontend acceptance:
- Mobile-first layout and coherent navigation.
- All visible controls have a defined action and state.
- No dead buttons or false success states.
- Screens include loading, empty, error, and access-denied states where relevant.
- Map and feed context can be navigated without implying unverified live tracking.
- Use real provider SDKs or clearly labelled development fixtures; never disguise fixtures as live information.

### Day 2 — Backend and integrations (2026-11-04)

Implement the smallest secure backend that supports the Day 1 user journeys.

Core domains:
- Account identity, session, profile, and optional page ownership.
- Posts and media metadata; upload/storage integration.
- Follows for people, pages, places, routes, stages, and communities.
- Feed retrieval and basic relevance ordering.
- Likes, comments, saves, and shares/attribution where supported.
- Place and map entity lookup.
- Road/incident reports with source, observed/published timestamps, status, evidence, and expiry.
- Business/provider listings and self-declared profile information.
- Community membership and discussions.
- Basic direct messaging and message permissions.
- Notification records and push delivery integration where credentials/permissions are available.
- Reporting, blocking, and minimum moderation controls.

Backend acceptance:
- Persist data in the selected database; do not use local-only state as the source of truth.
- Enforce ownership and access on the server/database, not only in the UI.
- Validate all user input and uploaded media.
- Keep current location separate from followed places.
- Make location sharing optional, permissioned, revocable, and off by default.
- Never infer vehicle movement or provider availability from a passenger's phone or a static listing.
- Use deduplication and expiry for incident events and notification jobs.
- Record errors and delivery outcomes; never report success without provider/backend confirmation.

### Day 3 — Integration, verification, and pilot finish (2026-11-05)

Connect the screens to real backend operations and verify end-to-end journeys.

Required journeys:
1. Create account/session → complete profile → publish a post → another account sees it in the feed.
2. Follow a creator → see eligible new content in Following/discovery.
3. Follow multiple places (for example Mandera, Mombasa, and Busia while physically in Nairobi) → discover relevant public content without changing or exposing physical location.
4. Publish a road incident → persist it → show it on the appropriate map/feed surface with source/time/status → deduplicate related reports.
5. Create a provider/boda profile → publish self-declared service information → make the profile discoverable without claiming automatic dispatch or confirmed availability.
6. Join a community → publish or reply to a discussion under its visibility rules.
7. Send and receive a permitted direct message.
8. Generate a meaningful notification event → record delivery attempt and outcome; test in-app delivery even if external push credentials are unavailable.

Day 3 verification:
- Test on real mobile viewport/device sizes.
- Test account boundaries and unauthorised access.
- Test upload failure, slow network, retry, and duplicate submission.
- Test map/location permission denied and revoked.
- Test incident expiry, dispute/correction, and duplicate reports.
- Test notification preferences and deduplication.
- Fix launch-blocking defects; document known limitations.
- Deploy a pilot only after the actual build and critical user journeys pass.

## 4. Proposed implementation architecture

**Recommended approach:** mobile client + modular backend (modular monolith) + managed infrastructure + asynchronous workers. Do not begin with microservices.

### Client
- React Native + Expo + TypeScript for Android and iOS is the recommended cross-platform route.
- Reuse mature navigation, media picker/camera, map, and query/state libraries.
- Keep UI, domain logic, API access, and provider adapters separated.

### Backend and data
- PostgreSQL as the source of truth.
- PostGIS for spatial queries and geographic entities.
- Managed authentication, database, object storage, and realtime capabilities where they fit.
- Server-side APIs/functions for authorization-sensitive operations.
- Durable background jobs/outbox for media processing, notification fan-out, and incident deduplication/expiry.
- Start with a modular monolith; split services only when load, team boundaries, or reliability requirements justify it.

### Managed integrations to evaluate and configure
- **Authentication:** managed email-based authentication. Product direction is no OTP; exact email method (password, passkey, email link, or another method) remains open and must be decided before implementation. Do not silently add OTP.
- **Video:** managed video upload/transcoding/streaming provider (evaluate Mux or Cloudflare Stream); use object storage/CDN for other media as appropriate.
- **Maps:** Mapbox or Google Maps, selected after checking SDK support, pricing, geographic coverage, and licensing.
- **Push:** FCM for Android and APNs for iOS.
- **Realtime:** managed realtime for appropriate chat/presence/update use cases; do not treat a transient realtime channel as the durable event/job queue.
- **Hosting:** Vercel for suitable web/API/admin workloads; mobile app distribution remains through the mobile build/release pipeline.

These are architecture recommendations, not confirmation that provider accounts, credentials, pricing, or integrations are already configured. Select the fewest services that can meet the pilot requirements. Avoid vendor sprawl.

## 5. Product scope for the first pilot

### Core pilot
- Accounts and personal profiles.
- Short-form video, photo, and text publishing.
- Feed, creator profiles, follows, likes, comments, and saves.
- Global discovery with local relevance.
- Multi-place following independent of current location.
- Explore map and place/route/stage discovery.
- Pulse with community road/incident reports and source/freshness/status.
- Basic location-aware in-app notifications; push where configured and consented.
- Basic provider/business directory and independent provider profiles.
- Basic communities and discussions.
- Basic direct messaging.
- Minimum trust, safety, privacy, reporting, and blocking controls.

### Explicitly limited or deferred
- Advanced personalised recommendation/ML ranking.
- High-scale livestreaming and advanced live moderation.
- Automated emergency dispatch or ambulance/police integrations.
- Unverified live GPS tracking or passenger-phone-as-vehicle-tracker behaviour.
- Fare custody, wallets, escrow, settlement, or payment distribution.
- Complex advertising marketplace and creator payouts.
- Global-scale reliability certification and advanced analytics.

A deferred feature may have a visible entry point only if the UI clearly communicates its actual state. Do not ship fake functionality.

## 6. Social discovery and place-follow invariants

- Social participation is central; VibeMat is not a map-first taxi or fleet-management app.
- Anyone may join and publish eligible content; transport employment or vehicle ownership is not required.
- One account may support optional additional profiles/pages.
- Short-form video is the initial media priority.
- Users can follow multiple places regardless of current location.
- Current location and followed places are separate concepts.
- Location is a relevance signal, not a global discovery restriction.
- Content from a creator in Peru may trend among Kenyan users when relevant.
- A place follow does not grant private access or guarantee every post/alert.
- Popularity is not proof of incident truth.
- Incident information must carry source, time, status, freshness, and correction/expiry handling.
- One underlying incident should be deduplicated even when many people report or receive it.
- Push/SMS must be preference-, consent-, relevance-, severity-, and frequency-aware; do not send an alert for every post or comment.
- Provider listings and self-declared availability are not dispatch, booking, or guaranteed service.

## 7. Money and provider boundary

VibeMat does not collect, hold, escrow, settle, or distribute passenger fares or transport-provider payments. Users pay providers through their existing authorised channels. Listings, discovery, and contact do not imply booking or confirmed fulfilment. Any future change requires a separate explicit product and legal decision.

## 8. Build rules

1. The VibeMat GitHub repository is the single source of truth for scope, decisions, implementation notes, and verification evidence.
2. Work in small, reviewable commits and branches; do not make unreviewed production changes.
3. Build the frontend on Day 1, backend on Day 2, integration/verification on Day 3, as the owner-directed timebox.
4. Reuse proven libraries and managed services; do not reinvent commodity infrastructure.
5. Do not expand scope during the sprint without recording the trade-off.
6. Do not mark a feature complete until its real end-to-end journey passes.
7. Do not claim pilot readiness from mockups, preview links, passing unit tests alone, or seeded demo data.
8. Keep secrets out of Git; use environment configuration and least-privilege credentials.
9. Apply server-side authorisation and privacy-by-default to all sensitive data.
10. Record blocked integrations and known limitations explicitly.
11. No fake buttons, fake live status, fabricated incident confirmation, fabricated availability, or false delivery success.
12. The three-day target is a delivery constraint, not permission to bypass security, user consent, data integrity, or truthful status.

## 9. Completion definition

The three-day sprint is complete only when:
- The app builds and launches in the intended mobile environment.
- Core pilot journeys above work against the real backend.
- Critical permission and privacy boundaries are tested.
- Upload, feed, follow, place discovery, incident reporting, community, and messaging flows have verified outcomes or explicitly documented exclusions.
- No critical/high-severity known defect blocks safe pilot use.
- Deployment and pilot access are verified, with evidence recorded in the repository.
- Remaining limitations, provider dependencies, and next steps are documented.

**Important:** this document sets the build target. It does not certify that any code, service, integration, or deployment exists or has passed these checks.
