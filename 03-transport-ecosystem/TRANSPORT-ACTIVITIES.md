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
