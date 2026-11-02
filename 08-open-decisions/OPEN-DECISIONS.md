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
