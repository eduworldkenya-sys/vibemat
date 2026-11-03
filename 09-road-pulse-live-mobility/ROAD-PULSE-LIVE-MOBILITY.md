# Road Pulse, Routing, Live Mobility, and Travel Logs

## Status and scope

**Agreed product direction:** VibeMat includes a community-powered road intelligence system (Road Pulse), normal and predictive routing, operator-authorised privacy-processed live vehicle streams, and user-controlled Travel Logs.

This document extends the existing living-map, transport-intelligence, and data-engine architecture. It is a product specification, not evidence that these capabilities are implemented. Application coding and deployment remain out of scope until the blueprint and first-release scope are sufficiently defined.

## 1. Six mobility concepts on one map

Represent the transport network as six understandable concepts, grouped into map layers rather than six disconnected products:

| Concept | Representation | What it means |
|---|---|---|
| Bus | Vehicle marker/activity | Public passenger transport, declared routes and journeys, operator updates, and authorised live movement |
| Lorry/truck | Vehicle marker/activity | Goods and cargo movement, declared journeys, loading activity where published, and relevant road impact |
| Motorbike/boda boda | Vehicle/service activity | On-demand or stage-based two-wheel transport activity; availability only when explicitly declared |
| Pavilion/stage | Place/infrastructure marker | A mapped waiting, boarding, shelter, pickup, or transport-support location |
| Pedestrian | Walking network/layer | Footpaths, crossings, walking connections, and pedestrian-relevant conditions |
| Commuter | Person/journey context | The traveller's planned, active, saved, or recorded journey; not a vehicle marker and not a public identity trace |

The map legend must distinguish a mapped place from a vehicle, a declared journey, a user report, a verified observation, an authorised live position, and historical aggregate. A marker never implies availability or live movement unless its source supports that claim.

## 2. Map-first interface and full-screen swipe

- Opening state: full-screen living map, with a compact bottom panel previewing nearby transport and relevant intelligence.
- Swipe up: expand discovery and journey planning into a full-screen panel that covers the map.
- Swipe down: dismiss the expanded panel and return to the map.
- The expanded panel may scroll internally. The map should not become a long dashboard page.
- Provide visible accessible expand/collapse controls; do not make gestures the only way to navigate.
- Preserve map position and layer state when returning from the expanded view.
- Avoid accidental map panning while the user is dragging the panel. Define clear gesture zones and touch behaviour.

## 3. Normal and predictive routing

### Normal route

A deterministic route through the available mapped network: roads, walkways, stages, and supported transport connections. Present route geometry, steps, transfers, and known gaps. Normal routing must not claim that a bus is available or that a departure is guaranteed merely because a route exists.

### Predictive route

A time-aware estimate of likely journey conditions. Depending on available evidence, it may consider:

- Expected congestion by road segment and direction.
- Fresh Road Pulse observations and active incidents.
- Expected waiting or stage activity, only where a credible data source supports it.
- Declared transport departures and connections, clearly labelled as declarations.
- Time-of-day and historical travel patterns.
- Weather or road restrictions only from identifiable, sufficiently fresh sources.

Present an estimated duration or arrival range, confidence/uncertainty, source and last-update time. Explain material route differences. If evidence is insufficient, say prediction is unavailable and retain the normal route. Never present a prediction as a guarantee or invent live availability.

## 4. Road Pulse: community-powered road observations

### Purpose

Road Pulse builds a continuously refreshed picture of road conditions from people already travelling on the network: bus passengers, drivers, boda riders, other motorists, and authorised transport sources.

### Report types

- Smooth flow.
- Slow/heavy traffic.
- Accident or incident.
- Road hazard or obstruction.
- Roadworks or closure.
- Road cleared / incident resolved.
- Other transport-relevant disruption, subject to moderation.

A report should be quick to submit and may include a structured category, optional short description, road segment, direction of travel, observation timestamp, location precision, source type, and optional evidence.

### Example: Muthiaga

A bus carrying ten VibeMat users passes Muthiaga. Four passengers report an accident. A motorist in an oncoming vehicle independently confirms seeing the incident. VibeMat groups the reports around the same road segment and event, recognises that the four passenger reports are correlated because they came from one bus, and treats the oncoming vehicle as a distinct source. The system can show multiple witnesses and independent-source corroboration without pretending that all five reports are five fully independent vehicles.

### Corroboration and conflicting observations

- Cluster reports that appear to describe the same event, segment, direction, and time.
- Correlated reports from one bus or shared vehicle can add witness detail but must not be weighted as fully independent sources.
- An observation from a different vehicle/source can add independent corroboration.
- Direction matters: a clear opposite-direction lane does not disprove an incident affecting the other direction.
- Smooth-flow reports do not erase an accident report. They may describe a different segment, direction, lane, or time.
- Keep the event state separate from the freshness of each observation.
- A report is evidence, not a verified fact merely because it has many confirmations. Protect against duplicate devices, coordinated manipulation, copied media, and false reports.

### Five-minute freshness rule

The agreed starting rule is a rolling **five-minute freshness window for each road observation**.

- Each observation is fresh for five minutes from its observation/submission time, subject to server-side timestamp validation and connectivity handling.
- A new valid observation refreshes the evidence picture; it does not rewrite the original report time.
- When an observation ages beyond five minutes without renewal, mark that observation stale.
- If all supporting observations become stale, the road state becomes stale/unconfirmed and should no longer be presented as current.
- **Expiry is not resolution.** An accident or hazard does not automatically disappear or become “road clear” after five minutes.
- A cleared/resolved state requires an explicit resolution report or sufficient new evidence under a defined verification policy.
- Show the latest observation time and the evidence/freshness status to users.

The five-minute window is a product default to validate in real use. Event-specific thresholds and offline submission rules remain open.

## 5. Photo, video, voice, and information evidence

A road report may include:
- A photograph.
- A short video.
- A short voice report.
- Text or structured additional information.

Evidence is attached to a specific observation and retains its source, capture/submit time where known, road segment/direction, and moderation/verification status. Do not treat several copies of the same photo or video as independent corroboration. Do not expose original media or reporter identity publicly by default. Apply file limits, malware/content checks, metadata minimisation, access controls, retention, and deletion policies before launch.

Reports should remain usable without media. Media must not make reporting slow or unsafe. Drivers must not be encouraged to handle a phone or camera while driving; passenger reporting and hands-free/voice-safe flows are preferred.

## 6. Operator-authorised live bus and vehicle streams

A bus operator or authorised fleet owner may opt into a live road-facing camera stream for a particular vehicle and an explicit sharing session. This is not an automatic feature of every installed bus camera.

### Public stream behaviour

- Prefer a forward-facing road view that helps people understand road and traffic conditions.
- Display the vehicle's published route/corridor context, stream source, live status, and freshness without exposing unnecessary exact vehicle or passenger information.
- The operator can start, pause, and stop the sharing session.
- A live stream can contribute candidate road observations, but automated detection is not automatically a verified incident.
- A stream going offline must be labelled offline/stale; do not freeze the last frame and imply it is live.
- Interior passenger cameras are private and must not be publicly streamed by default.

### Mandatory privacy processing before publication

The public delivery path must process the video before any viewer, thumbnail, cache, recording, or downstream consumer can access it. The processing requirements include:

1. Detect and blur/mask faces, including bystanders and children.
2. Blur/mask vehicle registration plates.
3. Detect and mask sensitive screens, documents, and other personal information where visible.
4. Disable audio by default; any audio capture or publication needs separate justification, controls, and legal review.
5. Apply privacy checks to every frame and to all derived media (preview images, clips, thumbnails, and replays).
6. **Fail closed:** if the privacy pipeline fails, cannot keep up, or falls below its quality threshold, pause public distribution. Never fall back to raw video.

Automated blurring is imperfect and does not itself establish a lawful basis. Require operator authority, appropriate notices and transparency, purpose limitation, data minimisation, security, access controls, retention/deletion rules, and review under applicable Kenyan data-protection requirements before launch.

## 7. Travel Logs: record the journey people actually made

Travel Logs are a separate user-controlled record of a journey, not a live road report and not a public tracking feed.

### Creation methods

- Manual: user enters origin, destination, mode, stops, time, and optional notes/media.
- Assisted: user explicitly enables journey capture for a defined period, reviews the generated route/timeline, edits it, and chooses whether to save it.

### A Travel Log may contain

- Origin and destination, with privacy controls.
- Approximate or actual departure/arrival times.
- Transport mode and optional operator/route.
- Stops, transfers, and route changes.
- Estimated or measured journey duration, clearly labelled.
- Personal notes and experience.
- Photos and videos the user chooses to attach.
- Completion state and creation/update timestamps.

### Visibility and sharing

- Private by default.
- User may share an individual log with a chosen audience/community or publicly.
- Sharing one log does not expose the user's entire history or enable continuous tracking.
- Protect home addresses, sensitive destinations, exact live whereabouts, and routine patterns.
- Allow correction, unsharing, and deletion subject to a documented retention/legal policy.

A user may deliberately submit a specific observation from a Travel Log to Road Pulse, but the two records remain distinct. A journey story does not become verified road evidence automatically.

## 8. Online and offline behaviour

- Cache eligible maps, routes, saved places, and previously retrieved information where licensing and device capacity permit.
- Label cached reports, streams, routes, and activity with their last-updated time.
- Do not show a cached report as live, a stale vehicle position as current, or a disconnected stream as live.
- A user may draft a report offline. Queue it visibly and submit it when connectivity returns; preserve the actual observation time separately from upload time.
- Late-arriving reports must be labelled delayed and must not silently replace current road state.
- Prevent duplicate submissions during retry and resolve conflicting offline edits.
- Live streaming and fresh predictive updates require connectivity; offline mode must state that they are unavailable and may use cached route information only.

## 9. Core records and lifecycle (conceptual)

| Record | Key information | Lifecycle |
|---|---|---|
| Road observation | Type, segment, direction, source, observed time, submitted time, evidence, freshness | Fresh → stale; may contribute to event resolution |
| Road event | Grouped observations, affected segment/direction, status, confidence, evidence links | Reported → corroborating → active/stale → explicitly resolved or disputed |
| Media evidence | Media type, owner/source, linked observation, processing/moderation status, retention | Uploaded → checked/processed → available/restricted → deleted/expired |
| Live stream session | Authorised operator/vehicle, camera view, start/stop, privacy pipeline health, audience policy | Requested → authorised → live → paused/stopped/failed |
| Travel Log | Owner, journey, stops, mode, media, visibility, timestamps | Draft → saved → optionally shared → edited/unshared/deleted |
| Route result | Network path, mode/transfer steps, data sources, estimate and confidence | Calculated → refreshed → superseded/stale |

These are conceptual product records, not a final database schema.

## 10. Product and safety boundaries

- Do not use a passenger's phone movement as proof of vehicle movement.
- Do not infer a vehicle's availability from its presence or stream.
- Do not treat passenger count, device count, report count, or video views as interchangeable.
- Do not expose individual commuter identities, live home-to-destination traces, or private Travel Logs.
- Do not let popularity determine whether a road report is true.
- Do not use video streaming to expose or monitor passengers.
- Do not encourage unsafe recording by drivers or passengers.
- VibeMat remains a transport discovery and intelligence network; this specification does not introduce fare collection, passenger wallets, dispatch, or payment custody.

## 11. Validation before implementation

Before coding or public launch, define and test:
- Road segment/direction matching and event clustering.
- Correlated versus independent source weighting.
- Five-minute freshness and stale/resolved transitions.
- Report abuse, moderation, corrections, and appeals.
- Prediction quality and confidence calibration against observed journeys.
- Route network coverage and offline licensing.
- Camera/operator authorisation and privacy-processing quality, including failure tests.
- Kenyan legal and data-protection review for public video, location, media retention, and assisted journey capture.
- Travel Log consent, visibility, editing, export, retention, and deletion.
- Low-data performance, battery impact, accessibility, and safe reporting.

No accuracy, live coverage, privacy-filter perfection, or production readiness is claimed until measured and independently reviewed.
