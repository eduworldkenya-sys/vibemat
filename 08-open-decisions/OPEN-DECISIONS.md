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
