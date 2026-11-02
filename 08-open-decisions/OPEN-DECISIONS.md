# Open Decisions and Product Backlog

This document is the product decision register. It distinguishes user-confirmed decisions from recommended defaults and unresolved decisions. A recommendation must not silently become a confirmed user decision.

## Confirmed product decisions

- VibeMat is a transport discovery and intelligence network.
- The architecture is hybrid: a living interactive map, a transport intelligence/discovery layer, and an underlying data engine.
- The map is the main app canvas.
- The first designed customer is Ken as a passenger.
- The transport ecosystem is one connected network, not separate apps for each participant.
- Dynamic transport activities and journeys are central to the product.
- Visibility, availability, commercial intent, planned journey, live movement, and historical activity are distinct concepts.
- A full or unavailable vehicle may still be discoverable as activity.
- Personalisation must not prevent exploration elsewhere.
- VibeMat will not handle passenger fares or transport money.
- Current work is product documentation only; no coding or deployment until the blueprint is sufficiently defined.
- Ken's dashboard is fundamentally a living transport map, not a conventional dashboard.
- The map should show all activity eligible for discovery across the visible map, while highlighting relevant opportunities.
- Open network discovery and personalised relevant-opportunity discovery must coexist.
- Operators control GPS sharing mode: approximate location, exact live GPS, or no GPS sharing. Exact live location is not public by default.
- Public discoverability does not grant permission for continuous precise tracking or permanent movement-history exposure.
- Proposed automatic stationary privacy threshold: **20 minutes**. After reliable stationary detection for 20 minutes, public exact GPS visibility is suspended and the last precise location is not displayed publicly. The owner/authorised operator can still access exact location in their authenticated account and may deliberately resume public sharing. A missing GPS update alone is not proof of parking.
- Ken's time-based dashboard should adapt to time, actual context, and available evidence, not assume a fixed commuter schedule.

## Ken's full-day experience — agreed direction

The map remains primary throughout the day. Time changes the emphasis, not the identity of the product.

| Time | Main emphasis | Passenger question |
|---|---|---|
| 5 AM | Morning preparation | How should I start my journey? |
| 8 AM | Active movement | What is happening along my journey and across the network? |
| 10 AM | Wider network discovery | What is happening across the transport network? |
| 2 PM | New activity and opportunities | What new transport activity or useful opportunity has appeared? |
| 4 PM | Return/next-trip preparation | What are my options for my next destination? |
| 6 PM | Evening movement | What has changed, and what should I consider now? |
| 9 PM | Tomorrow preparation and exploration | What should I know before tomorrow? |

This is a contextual emphasis, not a rigid schedule. If Ken works nights, travels midday, changes destination, or does not plan to travel tomorrow, the experience must adapt.

## Recommended defaults for the passenger experience

These are product recommendations based on the user's established preferences for simple, mobile-first, trust-first, explainable experiences. They are defaults for the blueprint, not claims of user approval.

- Show the map immediately; do not require a search before exploration.
- Use a compact, dismissible briefing rather than a large card dashboard.
- Keep open discovery available while highlighting relevant opportunities.
- Use time, permitted location/context, saved routes, and explicit interests together; do not infer certainty from routine.
- Allow inspection, saving/following, refinement, reporting, and publisher-enabled contact.
- Do not introduce booking, dispatch, fare custody, or payment handling into the passenger experience.
- Use opt-in, actionable, explainable notifications with quiet periods and frequency controls; avoid stale, duplicate, or low-confidence alerts.
- Preserve cached map/activity when possible, show last update, and never label cached data as live.
- Use high contrast, readable typography, clear hierarchy, generous spacing, accessible touch targets, consistent visuals, and fast low-data mobile behaviour.
- Recommended bottom navigation: Map · Discover · Insights · Profile. Final confirmation remains open.

## Still open — only notify the user when a real decision is needed

### Passenger experience
- Whether the user wants to change any of the recommended passenger actions or notification defaults.
- Whether the proposed bottom navigation is accepted.

### Map and data
- Map provider and licensing.
- Exact marker/legend design and map layers.
- Data providers for stages, operator activity, traffic, road conditions, and weather.
- Per-data-type freshness and expiry thresholds.
- Verification methods and minimum evidence for stage presence, movement, and availability.
- Handling of contradictory reports, duplicates, and appeals.

### Transport activities and participants
- Participant onboarding and identity verification.
- Which activity types and fields are mandatory for each transport category.
- Who may publish on behalf of a vehicle, operator, SACCO, or stage.
- Rules for recurring journeys, corrections, cancellations, and withdrawals.
- Public, restricted, invited, and private visibility policies by activity type.
- Detailed GPS permission, temporary sharing-session, retention, and access-audit rules.

### Intelligence
- First route-overlap/matching use case and evidence threshold.
- Confidence and uncertainty presentation.
- Personal trend definitions and minimum data thresholds.
- Ranking weights and evaluation criteria. No numeric weights are approved.

### Trust, safety, and compliance
- Reporting, moderation, impersonation prevention, and dispute workflows.
- Sensitive cargo/vehicle and safety-related exclusions.
- Data retention/deletion policy and authorised access rules.
- Applicable legal and regulatory review before launch.

### Business model
- What is free and what may be paid for.
- Rules for promoted activity and clear labelling.
- Operator services that do not compromise discovery or involve passenger fare custody.

### Identity and access
- User has indicated OTP should not be a requirement and email/custom authentication may be considered.
- Exact sign-in method remains open. No authentication implementation has been selected.

## Product documentation workflow

For every new idea:
1. Identify the problem or opportunity.
2. Identify affected users/participants.
3. Define proposed behaviour.
4. Define data, trust, privacy, and safety requirements.
5. Identify dependencies and conflicts.
6. Mark it as confirmed, recommended default, open, or rejected.

Do not code or deploy until the product blueprint and first-release scope are sufficiently defined. Product hypotheses must be tested with real passengers; do not claim retention, time savings, accuracy, or readiness without evidence.


## Additional confirmed product safeguards

- Passenger phone movement must never be used as a proxy for vehicle movement. A live vehicle movement claim requires a fresh source explicitly associated with and authorised for that vehicle.
- Vehicle GPS sharing remains under the vehicle owner/operator's choice: approximate location, exact live GPS, or none.
- Stage waiting information, if offered, must be an anonymous aggregate estimate with a bounded time window and minimum group threshold. No individual identity, location, device ID, arrival time, or waiting duration may be exposed.
- Device count must not be represented as passenger count without a validated estimation method. A stationary phone near a stage does not prove its owner is waiting.
- VibeMat's social layer is transport information discovery, not a chat or entertainment product. The map and following feed should present the same underlying transport activity from different discovery perspectives.
- Recommended account actions are follow, private save/pin, structured confirm, dispute/mark outdated, report, and share. Views are aggregate reach analytics only. Generic likes and popularity counts must not determine factual trust.

## Recommended social account model (not all formally approved)

The recommended first account model is:
- Follow operators, contributors, routes/corridors, stages, and selected activities.
- Save/pin routes, stages, activities, and insights privately by default.
- Confirm or dispute a specific report using structured feedback.
- Report unsafe, abusive, fraudulent, or misleading content.
- Share an item while preserving its original source, timestamp, and status.
- Show publishers aggregate reach analytics only; do not reveal individual viewers.
- Do not introduce public like counts, follower-count leaderboards, open comments, or direct messages as core VibeMat mechanics.

## Open decisions added by map/social design

### Stage estimate privacy and quality
- Minimum group threshold before a waiting estimate can be shown.
- Observation time window and expiry/freshness.
- Whether any privacy-preserving and lawful data source can estimate waiting passengers accurately enough.
- Validation method to distinguish people waiting from people living, working, passing through, or otherwise stationary near a stage.
- Retention and deletion rules for underlying signals.

### Social network and reputation
- Whether follow lists are private or allow user-controlled public visibility.
- Whether individual contributor profiles require identity verification and at what level.
- How independent confirmations are weighted and protected against coordinated manipulation.
- Whether comments or direct messages are excluded from the first release (recommended: exclude until moderation and safety are designed).
- Whether any positive reaction is needed beyond structured confirmation (recommended: no generic like in the first release).
- What aggregate publisher analytics are useful without exposing individual viewers.

### Map and feed
- Exact map/feed navigation and screen relationship.
- Whether a dedicated Discover feed is the first feed surface or map-integrated panels are sufficient for the pilot.
- Final map layers, marker legend, and per-data-type freshness thresholds.


## Business model and long-term relevance — recommended blueprint

### User groups and role-aware dashboards

VibeMat should support passengers, drivers, conductors, touts/stage contributors, transport creators/route MCs, SACCOs and fleet operators, parcel/cargo users, local merchants, and public/research partners. One person may participate in multiple roles; permissions should follow the activity and authority, not create disconnected apps.

The dashboard should be role-aware while sharing the same transport network:
- Passenger: map, departures, route/stage changes, followed sources, saved items and useful opportunities.
- Operator/SACCO: published activity, expiry/update tasks, aggregate reach, attributed enquiries and business tools.
- Driver/conductor/stage contributor: own updates, corrections, confirmation/dispute feedback, contribution history and assigned paid work.
- Creator/route MC: audience/reach analytics, published items, trust feedback, attributed enquiries/outcomes and eligible campaigns.
- Merchant: labelled campaign reach and privacy-safe area insights.
- Institutional/research partner: aggregate trends, coverage, confidence and methodology.

### Attention, intent, outcome and trust

Preserve separate measurement dimensions:
- Attention: impressions/reach, views and follows.
- Intent: saves/pins, enquiries, contact requests and deliberate interest.
- Outcome: credibly verified boarding, completed delivery or fulfilled service.
- Trust evidence: independent confirmations, disputes, corrections, source history and verification.

Do not use views, follows, likes or shares as proof of truth. A save is not a booking; an enquiry is not a completed journey. Generic likes are not required for the first release.

### Recommended revenue candidates (not approved prices)

- Operator/SACCO subscriptions for recurring business tools and workflows.
- Clearly labelled sponsored discovery, never buying verification or factual status.
- Qualified enquiry/campaign services with transparent attribution and outcome definitions.
- Operator-funded creator/route-MC campaigns, with the operator paying the creator directly.
- Local business advertising with privacy and relevance controls.
- Privacy-safe aggregate transport intelligence for eligible business or institutional customers.

The passenger's basic map, public discovery, essential safety/disruption information, source/freshness details, following, saving and reporting should remain free initially. VibeMat does not collect fares, hold funds, operate wallets or settle creator/operator payments. It may record non-financial attribution and charge for business services, subject to legal review.

### Retention and long-term relevance

Return visits should be driven by changing transport information, followed-source updates, route/stage changes, relevant journeys and capacity, creator explainers, new travel or cargo needs, and feedback on a user's own contributions. Useful information, opportunity, earning and enjoyable local storytelling can coexist. Entertainment must not incentivise misinformation, unsafe filming, artificial urgency or compulsive checking.

### Strategic acquisition hypothesis

Copying TikTok's feed is not an acquisition thesis. VibeMat's potential strategic value would come from a permissioned transport activity graph, trusted local contributors and operators, useful creator distribution, measurable demand/outcomes, repeat usage, network coverage and responsible data governance. A partnership, integration, investment, licensing arrangement or acquisition by TikTok or another company is possible in principle but not assumed or guaranteed. VibeMat should be built as a sustainable independent business first.

### Unresolved business decisions

- First paying customer segment and the first painful problem they will pay to solve.
- First monetisation experiment and measurable success criteria.
- What counts as a qualified enquiry and a verified outcome.
- Whether creator/MC campaigns belong in the pilot or a later phase.
- Operator subscription packaging and pricing.
- Sponsored placement rules, inventory limits and disclosure design.
- Whether institutional aggregate insights have a lawful, sufficiently accurate market.
- First launch participant mix and role permissions.
- How dashboard navigation and role switching should work.


## Confirmed business-model direction: first monetisation experiment

- First paying customer segment: **SACCOs and transport operators**.
- First commercial value to prove: **helping operators reach more passengers**.
- Initial experiment shape: one operator, one route/corridor, one measurable campaign.
- Basic passenger map and transport discovery remain free.
- VibeMat does not collect fares, hold passenger funds, or settle transport payments.

This is an agreed starting hypothesis. The specific operator, route, campaign format, attribution method, success thresholds, and pricing remain open and must be defined before a pilot is represented as commercially validated.

## Next blueprint activity: first release and pilot scope

Define the smallest end-to-end VibeMat release that can test passenger usefulness, operator publishing value, trustworthy transport information, and the first operator-reach experiment without prematurely building every role or revenue stream.
