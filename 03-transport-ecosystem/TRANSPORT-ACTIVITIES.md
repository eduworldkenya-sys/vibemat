# Transport Ecosystem and Activities

## One connected network

VibeMat is intended to connect the transport ecosystem in one network. Potential participants include:

- Passengers.
- SACCOs and bus operators.
- Touts and stage agents.
- Drivers and riders.
- Vehicle owners.
- Matatu and bus operators.
- Boda boda operators.
- Taxi operators.
- Private car owners.
- Pickup and van operators.
- Lorry and truck operators.
- Logistics, parcel, and cargo operators.
- Stages and transport support services.

The first designed customer experience remains the passenger experience. Other participant workflows will be documented in later product work.

## Dynamic transport activity

Participants should be able to publish what they are doing or planning, rather than relying only on static profiles or listings.

Example declarations:
- “I am going to Nanyuki at 10:00 AM. I have space to carry two sacks.”
- “I am going to Nanyuki at 10:00 AM. I am already full.”

Both are transport activity and can contribute to discovery and intelligence. The second declaration does not offer spare capacity, but the journey may still be relevant to understanding movement.

## Activity information

A transport activity may include:
- Participant or publishing source.
- Vehicle or transport mode.
- Origin and destination.
- Route or corridor declaration.
- Planned departure time.
- Journey or activity status.
- Capacity declaration.
- Whether new requests are being accepted.
- Commercial intent.
- Media such as photos or videos.
- Updates and corrections.
- Completion or withdrawal time.
- Source and timestamp.
- Visibility and privacy settings.

Not every activity must have every field. Missing information should remain missing rather than being invented.

## Flexible journey patterns

The product must allow different patterns, including:
- One-time journeys.
- Everyday or recurring journeys.
- Existing operating routes.
- Prospective routes.
- Occasional journeys.
- Return journeys.
- Flexible journeys.

Do not force every vehicle or operator to register only one fixed route. A vehicle may make different journeys and an operator may change plans.

## Activity lifecycle

A basic conceptual lifecycle is:

**Publish → Discover → Update → Complete or Withdraw → Retain eligible history**

The record should preserve relevant timestamps and status changes. A withdrawn or completed activity must not continue to appear as currently available.

## Separate concepts

These concepts must not be collapsed into one status:

| Concept | Meaning |
|---|---|
| Visibility | Whether an activity may be discovered by others |
| Availability | Whether the provider is accepting new requests |
| Commercial intent | Whether the provider is seeking customers or work |
| Planned journey | An intended future trip |
| Published journey | A journey declared by a participant |
| Live movement | A current position supported by a live source and timestamp |
| Historical activity | A past event, never presented as live |
| Attention | Views or follows |
| Intent | Saves, enquiries, requests, or contact |
| Outcome | A boarding, delivery, or other completion event |

A full lorry may still be discoverable as a journey. It should not be presented as having available cargo capacity.

## Open design questions

- Which activity types can each participant publish?
- Which fields are mandatory for each activity type?
- How are recurring journeys updated or paused?
- How are conflicting declarations handled?
- How should a participant correct a wrong location or departure time?
- Which activities can be published anonymously or with limited identity?

## Activity data that can support a passenger's morning decision

Transport activity may support passenger discovery when it includes relevant time and place context. Examples include:
- A bus or matatu operator publishing a planned departure.
- A driver declaring a recurring route or an occasional trip.
- A provider explicitly indicating spare capacity or that they are full.
- A stage agent or trusted source publishing a recent stage update.
- A participant reporting a road disruption or route change.

A declaration is not proof of physical presence or movement. Activity records should preserve who supplied the information, when it was supplied, its status, and any subsequent correction.

For a stage, distinguish at minimum:
- Stage exists as a mapped place.
- Operator or vehicle is associated with the stage.
- Vehicle is reported present.
- Vehicle is independently/technically verified present.
- Vehicle is accepting passengers or requests.
- Vehicle is preparing to depart.
- Vehicle has departed.

These are different facts and may require different evidence. Do not compress them into one “bus at stage” status.

## Proposed GPS stationary and public-presence lifecycle

GPS tracking state, physical vehicle state, and public map visibility are separate concepts.

Proposed behaviour when a vehicle's authorised GPS source detects that it has remained stationary:
1. After a configurable stationary threshold, classify the vehicle as **Parked / Stationary** if the evidence is reliable enough.
2. Automatically suspend public exact-GPS visibility and stop presenting the last precise coordinate as a current public position.
3. Keep the exact position available only to the vehicle owner or authorised operator in their authenticated account, according to permissions.
4. Allow the owner/operator to deliberately resume public GPS sharing, optionally as a short time-limited session.
5. When the vehicle moves again, do not silently assume public sharing should resume; apply the participant's sharing preference and clearly communicate the resulting status.

The system must distinguish:
- Moving with authorised live GPS.
- Parked / stationary.
- Public GPS sharing paused by the stationary rule.
- GPS/device offline or signal unavailable.
- Location stale / state unknown.
- Operator deliberately sharing a temporary live session.

A missing GPS update is not, by itself, proof of parking. GPS jitter, poor reception, device power loss, and temporary network interruption must be handled without inventing a stationary state.

**Agreed default threshold: 20 minutes.** After reliable stationary detection for 20 minutes, public exact-GPS visibility is suspended and the last precise coordinate is not shown publicly. The owner/authorised operator retains exact-location access in their authenticated account and may deliberately resume sharing. Category-specific rules and temporary-session duration remain open. This is a product rule, not an implemented GPS capability.

This is a proposed privacy and activity-state rule, not an implemented GPS capability.


## Vehicle movement versus passenger presence

A phone moving through space does not establish that a vehicle is moving. A passenger travelling in a matatu has a moving phone too. Therefore:

- Vehicle movement evidence must originate from the vehicle's own device or a driver/operator device explicitly authorised and associated with that vehicle.
- The vehicle owner/operator controls whether the vehicle shares approximate location, exact live GPS, or no GPS.
- A passenger's phone must never be used as an implicit vehicle tracker or as proof of vehicle movement.
- A user report may say a vehicle was observed at a place, but it remains a report unless independently supported by an authorised source.

## Privacy-preserving stage waiting estimates

VibeMat may eventually show an estimate such as “People waiting at this stage: approximately 3” only when the system has a legitimate, privacy-preserving basis to produce it.

Requirements:
- Aggregate only; never display who is waiting.
- Never expose an individual's coordinates, identity, device identifier, arrival time, or waiting duration.
- Use a bounded time window and minimum group threshold before displaying any count.
- Suppress small groups and sparse observations rather than revealing or implying an individual.
- Label the result as an estimate and show its observation window/freshness.
- Do not equate detected phones with people; account for multiple devices, people without phones, and uncertainty.
- Do not infer waiting merely because a phone is stationary near a stage. A person may live, work, pass through, or be waiting for something else.
- Do not infer vehicle presence or movement from passenger-device signals.

Exact minimum threshold, time window, estimation method, consent basis, and retention policy remain open and must be privacy-reviewed before implementation. No individual waiting tracker is part of the product design.

## Social transport activity and feedback

Transport information is the content of the social network. A publisher may share a journey declaration, departure update, stage observation, road disruption, capacity update, correction, or other transport-relevant report. Each item retains its source, timestamp, type, status, and evidence.

Users may follow:
- Operators and transport organisations.
- Individual contributors, subject to identity and safety controls.
- Routes and corridors.
- Stages and transport locations.
- Specific activities or journeys where following updates is useful.

Recommended user actions:
- **Follow:** receive relevant updates from a source, route, stage, or activity.
- **Save/pin:** privately keep an item, route, stage, or insight for later.
- **Confirm:** submit a structured independent confirmation of a report.
- **Dispute/correct:** flag that information appears wrong, outdated, or contradicted.
- **Report:** flag unsafe, abusive, fraudulent, or otherwise policy-violating content.
- **Share:** pass a transport item to others with its source and timestamp intact.

Views can support aggregate reach and publisher analytics, but are not evidence of truth. Generic likes should not determine trust or ranking. Comments and direct messages are not assumed in the first design; they need separate moderation and privacy decisions.

## Transport publishing as a creator and discovery network

VibeMat's confirmed social product direction uses a TikTok-style creator and discovery model adapted to transport. Transport activity and useful transport information—not generic entertainment—are the content.

Eligible publishers may include kamagers/touts, stage contributors, drivers, conductors, SACCOs/operators, route MCs, and other authorised transport contributors. Depending on their role and authority, they may publish:
- Vehicle/departure and seat/capacity updates.
- Stage and route conditions.
- Road disruptions and corrections.
- Route explainers and practical transport stories.
- Operator-authorised live or recorded updates.
- Journey, parcel, cargo, or service opportunities.

Each post/activity must retain its source, publisher authority where relevant, timestamp, status, location/route context, evidence type, expiry, and visibility permissions. Media does not make a claim verified. A creator's reach does not establish accuracy.

The same underlying activity may appear on the map, in open discovery, and in a Following feed. Following personalises the feed but does not close off wider discovery.

A moving vehicle or its route can be useful context for a sponsored campaign, but VibeMat must not assume that passengers inside the vehicle are VibeMat viewers. Any claim about onboard audience or exposure requires a separate consented, reliable measurement method.
