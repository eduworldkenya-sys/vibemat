# Open Decisions and Product Backlog

This document prevents proposals from silently becoming product requirements.

## Agreed decisions

- VibeMat is a transport discovery and intelligence network.
- The product is map-first: the living map is the main app canvas.
- The product architecture has three connected foundations: map, intelligence layer, and underlying data engine.
- The first designed customer is Ken as a passenger.
- The transport ecosystem is one connected network, not separate apps for each participant.
- Dynamic transport activities and journeys are central to the product.
- Visibility, availability, commercial intent, planned journey, live movement, and historical activity are distinct concepts.
- A full or unavailable vehicle may still contribute to discovery and transport intelligence.
- Personalisation must not prevent exploration elsewhere.
- VibeMat will not handle passenger fares or transport money.
- Current work is product documentation only; no coding or deployment until the blueprint is sufficiently defined.

## Proposed, not yet approved

- Bottom navigation: Map · Discover · Insights · Profile.
- A discovery-card pattern floating over the map.
- Specific categories of map layers and transport markers.
- A wider operator and provider workflow after the passenger experience is defined.
- Optional business services or monetisation that do not involve fare custody.

## Open decisions

### Passenger experience
- What is the first useful action Ken can take after opening the app?
- Which information must be visible immediately at 5:00 AM?
- How should Ken compare nearby stages and route options without creating a booking system?

### Data and live status
- Which sources can provide stage activity?
- How can a vehicle's presence at a stage be confirmed?
- What qualifies as a live location?
- How should stale or contradictory data be handled?
- Which information can work offline, and how is freshness shown?

### Activities
- Which activity types are supported in the first release?
- What fields are mandatory for each type?
- How are recurring and flexible journeys represented?
- How are edits, cancellations, and withdrawals handled?

### Intelligence
- What is the first route-overlap use case?
- What evidence is required for a match?
- How are confidence and uncertainty communicated?
- What is the first useful personal trend?

### Trust and safety
- What verification levels exist?
- What is public, private, or shared by invitation?
- What are the reporting and moderation workflows?
- What location precision is safe for each activity type?

### Business model
- What is free?
- What could be paid for without compromising discovery quality?
- How will promoted activity be labelled?
- What services, if any, will be offered to operators?

### Identity and access
- The user has indicated that OTP should not be a requirement and that email-based/custom authentication may be considered.
- Exact sign-in method is **open**. No authentication implementation has been selected.

## Product documentation workflow

For each new idea, record:
1. The problem or opportunity.
2. The user or participant affected.
3. The proposed behaviour.
4. Data and trust requirements.
5. Dependencies.
6. Conflicts with existing decisions.
7. Status: agreed, proposed, open, or rejected.

## Current next product task

Continue refining Ken's passenger experience: identify the specific decisions and useful information VibeMat provides that Ken cannot get simply by walking to Eastmar, Allsops, or Drive-In stage. Do this before defining provider workflows or implementation.

## New product focus: Ken's 5:00 AM decision

**Agreed product requirement:** the product must offer meaningful decision-support before Ken reaches a stage. Merely displaying nearby stage names is insufficient because he already knows those stages.

**Proposed first use case:** a map-first morning briefing that compares available, trustworthy activity around Eastmar, Allsops, and Drive-In and provides relevant journey, road, traffic, and weather context when reliable sources exist.

### Decisions still open
- Which single passenger decision should the first release optimise: when to leave, which stage to walk to, which route to take, or which declared journey to inspect?
- What is the minimum reliable data needed to compare stage activity?
- Which stage/operator sources can publish updates, and how will their identity be verified?
- How fresh must a stage report be before it is shown as current?
- Should Ken choose a destination/time each morning, or can the app suggest a briefing from his own saved patterns?
- Which road/traffic and weather sources are acceptable?
- What should the app show when no reliable live data is available?
- Which functions should remain useful offline, and how should cached data be labelled?

### Validation requirement
The 5:00 AM experience is a product hypothesis until tested with real passengers. Measure whether it helps users make a better decision than their current process; do not assume daily retention or time savings.

### Next task
Specify the exact information hierarchy and interactions for Ken's morning map, then define the evidence/source requirements for every displayed status. Do not begin coding until these are agreed.
