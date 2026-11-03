# VibeMat

**Brand:** VibeMat  
**Tagline:** As We Move.  
**Product philosophy:** Everyone Moves.  
**Product definition:** A social media network for transport and the wider movement ecosystem.

VibeMat connects people, creators, commuters, vehicles, routes, stages, places, communities, organisations, and businesses through social publishing, discovery, and mobility intelligence.

## Project status

**Stage:** Day 1 mobile frontend implementation in progress  
**Delivery target:** Day 1 frontend (2026-11-03), Day 2 backend (2026-11-04), Day 3 integration, verification, and pilot finish (2026-11-05).  
**Source of truth:** This repository.  
**Current social specification:** [Social Network Product Specification v0.3](11-social-network/SOCIAL-NETWORK-PRODUCT-SPECIFICATION.md)  
**Build plan:** [VibeMat Three-Day Build Sprint](12-build-plan/THREE-DAY-BUILD-PLAN.md)  
**Mobile frontend:** [Expo app entry](App.tsx) · [Main mobile experience](src/Main.tsx) · [Frontend setup](frontend/README.md)

The three-day target is a working pilot build, not a claim of global-scale readiness or production certification. Features count as complete only after their real end-to-end journeys work against persisted backend data and appropriate permissions.

VibeMat is one mobile-first social network—not a collection of separate apps for commuters, drivers, matatus, buses, or businesses. Anyone can join and participate, subject to platform rules. One account can support optional additional profiles and pages.

## Current implementation status\n\nThe mobile frontend scaffold and initial screen implementation are being developed on `feat/mobile-frontend-day1`. Current UI surfaces include Home/feed, Pulse, Explore/map preview, Create/media picker, Communities, Profile, and Inbox. Map tiles, real video playback, account data, publishing, messaging, live incidents, and server-backed follows are not yet integrated. Demo content is explicitly illustrative. Do not treat this branch as a completed or tested frontend until the app has been installed, typechecked, launched, and exercised on target devices.\n\n## Product thesis

VibeMat is social media for transport. People come to watch, publish, follow, discuss, share, and discover the people, stories, vehicles, routes, places, communities, and activity of a world in motion.

The consumer product is an Android and iOS app. Its home experience is hybrid: social feed and mobility intelligence both have first-class presence. The dedicated Explore map and map/location content inside the feed connect social discovery with geographic movement context.

## Confirmed product decisions

- Anyone can join; transport employment or vehicle ownership is not required.
- One account, with optional additional profiles/pages.
- TikTok-style social participation and creator discovery adapted to transport.
- Short-form video is the initial video priority.
- Video, photo, text, livestream, map/location posts, and structured transport information are in scope for product design.
- A dedicated Explore map and map/location content inside the feed.
- Businesses from all sectors may participate.
- Direct messages and community discussions are part of the product direction.
- The consumer product is an app, not a consumer website.
- Users may follow multiple places independently of their physical location.
- Global discovery is not restricted to a user's current location.
- The owner has selected a three-day build sequence: frontend, backend, then integration and product completion.

See the social specification and build plan for the distinction between agreed decisions, recommendations, and open questions.

## Hybrid product foundations

1. **Social network:** accounts, profiles, follows, content, creators, communities, messaging, and business pages.
2. **Movement discovery:** people, vehicles, routes, stages, places, events, and relevant content discovered through feed, search, and map.
3. **Mobility intelligence:** Road Pulse, time-sensitive transport information, movement context, and evidence-aware insights.
4. **Data and trust engine:** source, timestamps, freshness, permissions, verification, privacy, and history underpin social and mobility surfaces.

The map is a major shared interface, but it does not replace the social feed or define the whole product.

## Architecture direction

Use a mobile client with a modular backend and managed infrastructure. Reuse established video, map, storage, authentication, realtime, and push-notification services rather than reinventing commodity technology. Begin with a modular monolith and durable background processing; do not introduce microservices without demonstrated need.

The build plan lists candidate technologies and integrations. Provider selection, credentials, pricing, and exact authentication method must be verified before implementation. The product direction is no OTP and a customised email-based approach; the precise email authentication method remains open.

## Non-negotiable money boundary

VibeMat will not collect, hold, escrow, settle, or distribute passenger fares or transport payments. Passengers pay transport providers directly through their existing channels. Any future change requires a separate explicit product decision and legal/technical review.

## Documentation map

- [Product vision](00-vision/PRODUCT-VISION.md)
- [Product architecture](01-product-architecture/PRODUCT-ARCHITECTURE.md)
- [Social network product specification v0.3](11-social-network/SOCIAL-NETWORK-PRODUCT-SPECIFICATION.md)
- [Global, local, and multi-place discovery decision](11-social-network/GLOBAL-LOCAL-PLACE-DISCOVERY-DECISION.md)
- [Three-day build sprint](12-build-plan/THREE-DAY-BUILD-PLAN.md)
- [Ken: passenger experience](02-ken-passenger-experience/KEN-PASSENGER-EXPERIENCE.md)
- [Transport ecosystem and activities](03-transport-ecosystem/TRANSPORT-ACTIVITIES.md)
- [Discovery and intelligence](04-discovery-intelligence/DISCOVERY-INTELLIGENCE.md)
- [Map and interface](05-map-experience/MAP-AND-INTERFACE.md)
- [Business model boundaries](06-business-model/BUSINESS-MODEL.md)
- [Privacy and trust](07-privacy-and-trust/PRIVACY-AND-TRUST.md)
- [Road Pulse, routing, live mobility, and Travel Logs](09-road-pulse-live-mobility/ROAD-PULSE-LIVE-MOBILITY.md)
- [Social mobility marketplace](10-social-mobility-marketplace/MOBILITY-MARKETPLACE.md)
- [Open decisions and backlog](08-open-decisions/OPEN-DECISIONS.md)

## Decision language

- **Agreed** — explicitly established as a product requirement.
- **Recommended** — proposed product direction; not yet approved.
- **Open** — unresolved; do not silently assume an answer.
- **Rejected** — explicitly ruled out.

New ideas should be documented with their problem, intended behaviour, affected participants, dependencies, conflicts, and decision status. Do not turn an unapproved proposal into an agreed requirement.

## Working method

The repository is the single source of truth for product scope, architecture decisions, implementation notes, and verification evidence. The owner-authorised build sequence is frontend on Day 1, backend on Day 2, and integration, testing, and pilot completion on Day 3. Reuse proven services, work in reviewable changes, and do not bypass security, privacy, or real end-to-end verification to meet the timebox.

## Core product test: Everyone Moves

Every major product decision must be tested against the needs, authority, and real tasks of the relevant movement participants—not only a passenger. A commuter may discover a journey; a driver may publish authorised activity; a creator may tell transport stories; an operator may publish service information; a logistics business may share its work; and a community contributor may share a road observation.

The product must preserve each participant's permissions, responsibilities, privacy, and independent business model. No role is mandatory to join or participate in the social network.

## Reconciliation note

The repository contains earlier map-first and transport-discovery assumptions. The Social Network Product Specification v0.3 records the newer owner-confirmed social-media direction and hybrid home decision. Where older documents conflict with v0.3 and the three-day build plan, the newer owner-approved decisions take precedence; reconcile older documents without silently changing their historical record.
