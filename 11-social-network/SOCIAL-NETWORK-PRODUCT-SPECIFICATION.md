# VibeMat Social Network Product Specification

**Status:** Product discovery / blueprint  
**Version:** 0.3  
**Brand direction:** VibeMat — As We Move.  
**Product philosophy:** Everyone Moves.  
**Product definition:** A social media network for transport and the wider movement ecosystem.

This document records decisions explicitly confirmed by the product owner and separates them from recommendations and unresolved decisions. It does not authorise application implementation or deployment.

## 1. Product thesis

VibeMat is a social network organised around transport and movement. People use it to watch, publish, discuss, follow, discover, and connect with the people, vehicles, routes, places, communities, organisations, and businesses involved in movement.

VibeMat is not a taxi app, booking app, SACCO operating system, fleet-management system, or generic video platform with transport-themed posts. Social participation is the central experience. Movement discovery and intelligence make the network transport-native.

**Core promise:** Discover the people, stories, vehicles, places, communities, and activity of a world in motion.

## 2. Confirmed product decisions

The following decisions were explicitly confirmed:

| Area | Decision | Status |
|---|---|---|
| Home experience | Hybrid: social feed and mobility intelligence both have first-class presence | Agreed |
| Discussion priority | Complete the product blueprint before implementation | Agreed |
| Account access | Anyone can join, like TikTok; transport employment or ownership is not a prerequisite | Agreed |
| Account structure | One account, with optional additional profiles/identities | Agreed |
| Social model | TikTok-style open social network: anyone can watch, publish, follow, and interact subject to platform rules | Agreed |
| Content | Transport-related video, photo, livestream, map, route, and transport information | Agreed |
| Video launch format | Short-form video first | Agreed |
| Map relationship | A separate Explore map and map/location content embedded in the social feed | Agreed |
| Business participation | Businesses from all sectors may participate | Agreed |
| Messaging | Direct messages and community discussions | Agreed |
| Platform | Consumer product is a mobile app, like TikTok, not a consumer website | Agreed |

### Clarifications

- One account means one person does not need separate logins for commuter, creator, driver, or business participation.
- Optional profiles are additional public identities/capabilities under that account, not separate accounts. Exact profile types and switching behaviour remain to be specified.
- Anyone may create ordinary content. Claims of vehicle ownership, operator authority, professional status, or official organisation representation require appropriate verification before being displayed as verified.
- "Short-form video first" is the launch priority. Long-form video support is not approved or rejected yet.
- "All businesses" means the platform is open to businesses beyond transport. It does not mean every business automatically receives paid advertising, verification, or unrestricted reach.
- Mobile app means Android and iOS consumer experiences. Backend services, internal moderation/admin tools, and public information pages may still exist; they are not the primary consumer product.

## 3. Social identity and account model

### Recommended baseline

1. One account and authentication identity per person.
2. One default personal profile.
3. Optional additional profiles or managed identities where there is a legitimate need, such as a creator identity, business page, vehicle page, or organisation page.
4. A user may follow, publish, comment, and participate without selecting a transport occupation.
5. Business and organisation pages have authorised administrators and role-based permissions.
6. Verified claims are separate from ordinary account creation.

### Important distinctions

- **Account:** authentication, security, preferences, and ownership.
- **Personal profile:** the person's public social identity.
- **Additional profile/page:** a creator, business, organisation, vehicle, or other approved public identity.
- **Role/capability:** permissions granted to an account or page, not a mandatory account category.
- **Verification:** evidence-backed status for a specific claim; verification of a person does not automatically verify a vehicle, business, or post.

### Still to decide

- Which additional profile/page types launch.
- Whether one account may create multiple pages and how page ownership transfers.
- Age requirements and protections for younger users.
- Whether business pages can be created before verification, with clear unverified labels.
- Account recovery and the exact email-based authentication method. The product direction is no OTP; the specific password/passkey/email-link method has not been selected.

## 4. Social graph

The social graph should connect accounts and pages to people and movement entities.

### Followable objects

- People and creators.
- Business and organisation pages.
- Vehicles and vehicle pages.
- Routes and corridors.
- Stages, terminals, and places.
- Communities.
- Potentially events and recurring transport topics.

Following a route, vehicle, or community should behave like following a creator: eligible public posts and updates from that object can appear in the user's feed.

A follow relationship is not a booking, service subscription, endorsement, or proof of availability.

### Recommended relationship types

- Follow: receive eligible public content and updates.
- Join: become a member of a community with its membership rules.
- Administer: manage a page or community under granted permissions.
- Own/represent: a verified or claimed relationship to an entity, with evidence and audit history.
- Tag/mention: reference another account, page, place, route, or vehicle in content.

## 5. Content model

VibeMat should use one publishing system with different content formats and optional structured movement attachments.

### Initial content formats

1. **Short video:** vertical short-form clips.
2. **Photo:** single images and multi-image posts.
3. **Text:** stories, opinions, questions, discussions, and announcements.
4. **Livestream:** live video and associated discussion, subject to launch safety and moderation gates.
5. **Map/location post:** content attached to a place, stage, route, corridor, or permitted location.
6. **Movement information post:** structured road, route, stage, vehicle, trip, or service information.

### Structured movement attachments

A social post may optionally carry structured data such as:

- Place, road segment, direction, stage, route, or destination.
- Transport mode or vehicle reference.
- Observation/report category.
- Event time and publication time.
- Planned, observed, reported, operator-declared, verified, resolved, stale, or historical status.
- Source and evidence type.
- Visibility and location precision.

A video of traffic can remain a normal social post while also carrying a structured traffic observation. These are linked but not interchangeable records.

### Information integrity rule

Popularity, views, likes, comments, and shares do not establish truth. User-generated claims must not automatically become verified live transport information. Dynamic information must show source, time, status, and freshness. Structured reports require separate evidence, corroboration, expiry, dispute, and correction rules.

## 6. Feed and recommendation system

### Proposed feed surfaces

- **For You:** personalised discovery across eligible public content.
- **Following:** content from followed accounts, pages, vehicles, routes, and communities.
- **Nearby:** locally relevant content when the user permits or chooses location context.
- **Trending:** content gaining meaningful attention across a selected geography or topic.

These four surfaces are recommended and await explicit confirmation.

### Recommended ranking principles

- User interest and explicit follows should matter.
- Watch completion, replays, saves, shares, comments, and meaningful interactions may inform relevance, but should not be treated as independent proof of quality or truth.
- Freshness should matter more for time-sensitive movement updates than for evergreen entertainment or educational content.
- Location is an optional relevance signal, not a confinement mechanism.
- Users need controls such as Not Interested, hide creator, reduce topic, mute, and reset/refine recommendations.
- Safety, privacy, integrity, and legal eligibility are hard constraints, not ranking signals that can be outweighed by engagement.
- Paid placement must be labelled and separated from organic ranking and factual verification.
- Avoid incentives that reward dangerous driving footage, staged incidents, misinformation, harassment, or addictive engagement.

### Still to decide

- Exact feed tabs and default selection.
- Whether Nearby and Trending are launch features.
- Recommendation signals, weights, diversity, freshness, and frequency controls.
- How content from followed vehicles/routes/pages is blended with creator content.
- How to explain and control recommendations.
- Ad placement frequency and excluded contexts.

## 7. Communities

### Recommended community types

1. **Location communities:** towns, cities, neighbourhoods, and places.
2. **Route communities:** corridors and recurring routes.
3. **Transport communities:** matatu culture, boda boda, buses, trucking, taxis, pedestrians, and other modes.
4. **Interest communities:** road trips, vehicle photography, travel stories, road safety, and transport culture.

### Recommended capabilities

- Public discovery and preview.
- Follow without joining.
- Join/leave and membership rules.
- Posts, short videos, photos, and discussions.
- Community announcements.
- Moderators and administrator roles.
- Reporting, blocking, and moderation history.
- Search and related-community recommendations.

A route or stage community is a social destination, not an official operator or guarantee of transport availability. Official status requires evidence and clear labels.

### Still to decide

- Public, private, and approval-based community modes.
- Who can create communities and whether names/locations need moderation.
- Membership limits, moderator powers, and appeals.
- Whether community messaging is group chat, threaded discussion, or both.
- Whether communities can be sponsored and how sponsorship is disclosed.

## 8. Explore and movement map

### Confirmed direction

The map has two placements:
1. A dedicated map experience within Explore.
2. Map cards, location attachments, and relevant movement context inside the social feed.

### Recommended map-to-social interaction

- Tap a stage to see its public information, related posts, community, and relevant route content.
- Tap a route to see route-related posts, route community, and eligible movement information.
- Tap a public vehicle page/marker to see its profile and content, with location freshness and source clearly labelled.
- Tap a place to discover creators, communities, businesses, events, and content associated with it.
- A map marker may open the underlying social post or activity record.
- Users can move between map and feed without losing their selected area or context.

### Map truth and privacy rules

- Distinguish verified live, operator-declared, community-reported, estimated, cached, and historical data.
- A visible profile or marker does not imply availability or acceptance of requests.
- A planned journey is not a live vehicle position.
- Do not expose private exact locations by default.
- Vehicle tracking requires an authorised vehicle-associated source and explicit owner/operator permission.
- Ordinary users' live location sharing is optional, granular, revocable, and off by default.
- Stage activity must be aggregated and privacy-protected; never expose individual waiting persons or movement histories.

### Still to decide

- Map provider, map layers, offline behaviour, and data licensing.
- Exact marker categories and visual language.
- Search, filters, time windows, and map clustering.
- Whether vehicle/route pages and map entities are available at launch.
- Location permissions and retention policy.

## 9. Messaging and interactions

### Confirmed direction

Both direct messages and community discussions belong in the product.

### Recommended separation

- **Direct messages:** private one-to-one or small-group conversations between accounts, subject to privacy settings and abuse controls.
- **Community discussions:** public or member-visible conversations attached to a community, post, or topic.
- **Post comments:** conversation attached to a specific post.
- **Live chat:** discussion during a livestream, with moderation controls.

### Recommended controls

- Who can message: everyone, followers, followed accounts, or nobody.
- Message requests and spam filtering.
- Block, mute, report, restrict, and delete controls.
- Community moderators can moderate community discussions but should not access private messages without a legitimate safety process.
- Users should control read receipts, online status, and discoverability where appropriate.
- Safety escalation and evidence handling must be defined without promising absolute confidentiality where legal or safety obligations apply.

### Still to decide

- Whether direct messages launch immediately or after core feed/community functions.
- One-to-one, group, voice, image, video, and file support.
- Message request defaults and account age restrictions.
- Retention, deletion, reporting, encryption, and moderation design.
- Whether community conversations are threaded posts, live chat, or both.

## 10. Creators

### Confirmed direction

Creator participation should follow an open TikTok-style model: anyone eligible can create content and build an audience. A person does not need to be a transport professional.

### Recommended creator capabilities

- Public creator profile and follower network.
- Short-video publishing.
- Drafts and publishing controls.
- Content performance analytics.
- Audience and follower insights.
- Livestreaming when eligible.
- Creator discovery and topic/category labels.
- Optional business/brand campaign participation.
- Clear eligibility and safety rules for monetisation.

Transport-specific discovery categories may include matatu culture, travel, buses, boda boda, trucking, road reporting, vehicle photography, transport education, and mobility stories. Categories help discovery; they must not restrict ordinary publishing.

Creator monetisation is a future commercial decision, not an automatic launch promise.

## 11. Businesses and advertising

### Confirmed direction

Businesses from all sectors may participate. VibeMat is not restricted to transport businesses.

### Recommended participation model

- Any eligible business may create a business page.
- Business pages can publish organic posts like other pages.
- Businesses can build followers and participate in relevant communities.
- Paid advertising is a separate capability with eligibility, billing, disclosure, and campaign controls.
- Transport businesses may attach relevant routes, vehicles, services, and movement information where authorised.
- Non-transport businesses may participate through ordinary business content and advertising.

### Potential commercial models — brainstorm, not approved

- Sponsored posts and short videos.
- Promoted business pages.
- Local and contextual advertising.
- Sponsored community or event campaigns.
- Creator-brand collaborations.
- Business discovery placements.
- Campaign analytics and reporting.

### Guardrails

- Clearly label paid placements.
- Payment cannot buy verification, factual status, or guaranteed organic ranking.
- Protect essential safety/disruption information from ad displacement.
- Do not claim vehicle passengers saw an advert merely because a vehicle or route was associated with a campaign.
- Keep audience measurement honest and privacy-preserving.
- Existing no-fare-custody boundary remains: VibeMat does not collect, hold, escrow, settle, or distribute passenger fares or provider payments.

### Still to decide

- Whether businesses can self-serve page creation at launch.
- Business verification and admin roles.
- Ad account structure, payment rails, pricing, targeting, campaign objectives, moderation, and reporting.
- Which business categories are suitable for advertising and which are restricted.
- Creator compensation and campaign attribution.

## 12. Trust, safety, and privacy

The product may use familiar social-media controls, but must customise them for transport-specific risks.

### Baseline requirements

- Account reporting, blocking, muting, and restriction.
- Content reporting and moderation.
- Impersonation and identity/authority claims.
- Vehicle and business ownership/representation claims.
- Copyright and media rights complaints.
- Dangerous driving and unsafe filming rules.
- Accident and emergency content handling.
- Anti-harassment and anti-doxxing controls.
- Livestream moderation and termination.
- Location privacy and protection of home/work/sensitive places.
- Public media privacy processing and restrictions on exposing faces, number plates, passengers, and sensitive personal information.
- Road report correction, dispute, expiry, and source/freshness labelling.
- Sponsored content disclosure.
- Moderation appeals, audit trails, and incident response.

### Core principle

Adopt familiar social-media participation patterns, but do not copy engagement mechanics that encourage dangerous transport behaviour or misinformation. Safety and integrity must override reach.

## 13. Mobile application scope

### Confirmed direction

The consumer product is a mobile application, comparable in product form to TikTok, not a consumer website.

### Product implications

- Android and iOS applications.
- Mobile-first feed and vertical video playback.
- In-app camera, media picker, upload, and publishing.
- Map and location permissions.
- Livestream capture and viewing.
- Push notifications.
- Direct messages and community discussions.
- Accessibility, data-saving, battery, and network-resilience considerations.

Backend APIs, media processing, moderation consoles, business administration, and internal operations tooling are necessary supporting systems. Their existence does not change the consumer product's app-first identity.

The technical stack and native/cross-platform implementation choice remain open.

## 14. Proposed navigation

Recommended starting navigation, pending confirmation:

1. **Home:** hybrid entry with social feed and mobility intelligence.
2. **Explore:** discovery search and dedicated movement map.
3. **Create:** short video, photo, text, livestream, and movement update.
4. **Communities:** joined/followed communities and community discovery.
5. **Profile:** personal profile, optional pages, content, saved items, creator/business tools, and settings.

Home should expose both MoveFeed and Road Pulse/map context. The exact visual hierarchy, screen layout, and navigation labels remain open.

## 15. Product boundaries

VibeMat is:
- A social media network for transport and movement.
- A place to publish, watch, follow, discuss, and discover.
- A network connecting people, vehicles, routes, stages, places, communities, creators, and businesses.
- A mobile-first social product with movement intelligence and a map.

VibeMat is not:
- A taxi or ride-hailing operator.
- A SACCO or fleet-management system.
- A mandatory booking intermediary.
- A generic transport directory.
- A transport wallet or fare custodian.
- A generic entertainment clone with transport branding.

Provider discovery and external handoffs may be considered separately, but no booking, transaction, or provider integration is implied by this social specification.

## 16. Open decisions and next specification sequence

The following must be resolved before the blueprint is considered implementation-ready:

1. Final account/profile types and page permissions.
2. Exact post model, media constraints, and movement attachment schemas.
3. Feed surfaces, ranking principles, and launch scope.
4. Community visibility, creation, membership, and moderation.
5. Map entity types, marker rules, and map/feed interactions.
6. Messaging feature scope, privacy, and moderation.
7. Creator analytics and eligibility.
8. Business pages, advertising product, and commercial controls.
9. Safety policy, verification levels, and moderation operations.
10. App navigation and screen-by-screen user journeys.
11. Pilot audience, geography, content supply, and success metrics.
12. Technical architecture, infrastructure, cost model, and release plan.

## 17. Decision language

- **Agreed:** explicitly confirmed by the product owner.
- **Recommended:** proposed product direction; not yet approved.
- **Open:** unresolved; do not silently assume.
- **Rejected:** explicitly ruled out.

No feature should be described as implemented, available, verified, or production-ready based on this document. This is a product specification, not implementation evidence.
