# Product Architecture

## Agreed architecture: three connected foundations

### 1. Living interactive map

The map is the actual app canvas and primary interface—not a small card embedded in a dashboard.

It allows a person to:
- Pan and zoom across places.
- Explore roads, stages, locations, corridors, and routes.
- See transport activity represented spatially.
- Tap markers to inspect the underlying activity.
- Explore activity nearby or deliberately move to another area.

The map can show different kinds of transport and activity. It should not imply that every marker is a vehicle currently moving.

### 2. Transport intelligence and discovery algorithm

This layer interprets the underlying data and decides what may be useful to surface.

Potential responsibilities:
- Rank relevant discoveries.
- Identify route overlap and possible journey matches.
- Recognise stage and corridor activity.
- Aggregate movement patterns and heatmaps.
- Identify demand and capacity signals where data supports them.
- Build personal travel trends.
- Distinguish current, planned, reported, and historical activity.
- Support discovery across the map, not only near the user's current location.

The algorithm is a product capability, not a claim that every insight will be available at launch.

### 3. Underlying data engine

This is the foundation that makes the map and intelligence meaningful. It stores and governs records such as:
- People and participant roles.
- Operators, vehicles, and transport modes.
- Places, stages, roads, routes, and corridors.
- Transport activities and journey declarations.
- Origin, destination, departure, and status.
- Capacity and availability declarations.
- Commercial intent where relevant.
- Media and updates.
- Source, timestamp, freshness, and verification state.
- Permissions, privacy settings, and visibility.
- Historical records and aggregation eligibility.

## How the layers work together

1. A participant or trusted source declares or reports transport activity.
2. The data engine stores the activity with its source, time, status, and permissions.
3. The map presents the activity in its appropriate spatial and temporal context.
4. The intelligence layer evaluates relevance, overlap, patterns, and possible connections.
5. The discovery function selects and distributes useful findings to people or makes them explorable on the map.
6. The user inspects the evidence and decides what to do.
7. The activity can be updated, completed, withdrawn, or retained as appropriately labelled history.

## The four distinct responsibilities

These concepts are connected, but they are not interchangeable:

- **Data:** records what has been declared, reported, observed, verified, or stored historically. Data answers: “What information do we have?”
- **Intelligence:** interprets data to identify meaning, patterns, relationships, confidence, relevance, and possible implications. Intelligence answers: “What does this information suggest?”
- **Discovery:** decides which activities or insights to surface to which users, in what order and context. Discovery answers: “What should this person be shown now?”
- **Map:** gives people the spatial interface to see, navigate, inspect, and explore the transport network. The map answers: “Where is this happening, and what can I explore?”

The intelligence layer is broader than a ranking formula. Ranking is one tool within discovery. Intelligence also includes route-overlap detection, pattern recognition, stage/corridor analysis, trend analysis, and evidence interpretation.

## Core domain distinction

The core unit should be **transport activity**, not only a static vehicle or route listing. A vehicle, route, journey, capacity declaration, movement observation, media item, or operator profile may contribute to an activity record.

## Architecture constraints

- Do not treat a planned journey as a live vehicle position.
- Do not treat a historical route as current availability.
- Do not infer that a visible vehicle is accepting customers.
- Do not expose private exact locations by default.
- Do not create separate disconnected apps for each participant type.
- Do not make the map dependent on an unverified claim of real-time tracking.

## Status

**Agreed:** three-part architecture—living map, transport intelligence, and underlying data engine.

**Clarified product model:** data engine supplies evidence; intelligence interprets it; discovery distributes relevant findings; the map is the spatial interface.

**Open:** exact technical architecture, data providers, map provider, tracking mechanisms, and launch infrastructure. These are deliberately not being selected during the product-notes stage.

## Morning decision-support flow

The architecture should support a passenger decision cycle:

1. **Context:** establish the user's chosen/current map area and relevant time window, with permission-aware location use.
2. **Collect:** retrieve nearby stage, route, journey, vehicle/activity, road, traffic, and weather information only from available sources.
3. **Qualify:** label each item as operator-declared, user-reported, partner-supplied, verified live, estimated, or historical; attach timestamps and freshness.
4. **Interpret:** identify relevant departures, route alternatives, overlaps, and meaningful changes without converting estimates into facts.
5. **Present:** show a compact map-first briefing with expandable evidence and details.
6. **Decide:** let Ken inspect options and decide whether/when to leave or which stage/route to consider. VibeMat does not guarantee a seat or make the decision for him.

The system must degrade honestly: if live stage data is unavailable, show that it is unavailable rather than inventing stage readiness. If offline, show cached information with its last-updated time and disable claims that require a live connection.


## Vehicle movement and passenger-presence evidence boundary

- A moving phone is not evidence of a moving vehicle. A passenger's phone inside a moving matatu can produce the same phone-motion signal as a driver's phone.
- Vehicle movement may be claimed only from a source explicitly associated with and authorised for that vehicle, such as its own device or an authorised driver/operator device configured for that vehicle.
- The vehicle owner/operator chooses the public GPS mode: approximate location, exact live GPS, or no GPS sharing. A passenger's personal device must never silently become a vehicle tracker.
- Stage waiting information is a privacy-protected aggregate estimate, not person-level tracking. It may be shown only when a configured minimum group threshold and aggregation/time-window rules are satisfied.
- Never expose identities, individual coordinates, individual waiting duration, or a person's movement history through stage-waiting estimates.
- If evidence is insufficient, show that the information is unavailable or unknown; do not infer vehicle movement or passenger waiting from raw phone movement.

## Social transport information network

VibeMat also supports a social discovery model built around useful transport information. The social layer is not a separate chat or entertainment product: transport declarations, reports, corrections, confirmations, and updates are the content.

Users may follow transport sources and objects such as operators, contributors, routes/corridors, stages, and (where useful) specific activities. A personalised feed can surface new information from followed sources while the map continues to expose eligible activity across the wider network. Both views use the same underlying activity and evidence records.

Every item should identify its publisher/source, publication or observation time, information type (for example declaration, report, or verified update), current status, and evidence/freshness where relevant. Community feedback can help assess an individual post, but popularity must never be treated as proof of accuracy.

**Recommended interaction model:** follow, save/pin, share, and structured feedback (confirm, dispute, report incorrect/outdated/unsafe). Views may be measured as aggregate reach/analytics, not treated as trust. Avoid generic like-count competition as a primary transport signal. Free-form comments and direct messaging are not assumed; they require separate abuse, privacy, and moderation decisions.


## Road Pulse, routing, live media, and travel history

The product direction now includes a community-powered road intelligence capability called **Road Pulse**, normal and predictive journey routing, operator-authorised privacy-processed live vehicle streams, and user-controlled Travel Logs. The complete behaviour and safeguards are specified in [Road Pulse, Routing, Live Mobility, and Travel Logs](../09-road-pulse-live-mobility/ROAD-PULSE-LIVE-MOBILITY.md).

These capabilities extend the existing three-part architecture; they do not create separate apps or replace the living map.

- Road observations are evidence records with road segment, direction, source, timestamp, freshness, and verification state.
- Normal routing calculates a route from the mapped network and known transport connections. Predictive routing adds time-dependent estimates and confidence without presenting estimates as facts.
- Live video is a separately authorised media source. Only privacy-processed output may be distributed.
- Travel Logs are user-controlled journey records and remain distinct from live road reports.
- Offline data is cached and labelled with its last-updated time; offline state must never masquerade as live intelligence.


## Social mobility marketplace and consolidated transport economy

VibeMat's product identity is a **social mobility network and multi-provider marketplace**, not a map replacement and not a transport operator. It brings independent transport businesses, services, users, and mobility experiences into one discoverable ecosystem.

The marketplace is intended to accommodate multiple provider categories and their distinct business models, including:
- Ride-hailing and taxis (for example, Uber, Bolt, and independent taxi fleets).
- Intercity and scheduled bus operators (for example, 2NK, Mololine, and other coach/shuttle businesses).
- Matatus, SACCOs, city buses, and other public or informal transport.
- Boda bodas, motorcycle taxis, tuk-tuks, and local mobility providers.
- Car hire, vehicle rental, tours, travel and road-trip services.
- Parcel, courier, delivery, cargo, lorry, truck, and logistics businesses.
- Other mobility-adjacent services that genuinely serve transport needs.

These examples describe provider categories, not existing partnerships, integrations, availability, or endorsements. Each business remains independently owned and responsible for its own operations, prices, fulfilment, licences, customer service, and contractual terms.

### Consolidation means one ecosystem, not one operator

VibeMat provides a common layer for discovery, provider presence, social distribution, enquiries and authorised connections, and transparent commercial attribution. Actual service delivery and each provider's business model remain with that provider unless a separately approved integration explicitly changes that boundary.

A provider may participate through a basic public listing, a self-managed business profile, a structured activity feed, a booking/ticketing integration, or another authorised connection. Integration depth must be explicit per provider. A listing or link must never be presented as live inventory, confirmed availability, a booking, or a completed transaction.

### Social mobility experience

The social layer makes mobility experiences discoverable and shareable: road-facing dashcam clips, journey stories, route explainers, stage updates, travel logs, service announcements, and useful community observations. Content must be connected to relevant transport context where possible, with clear source, time, status, and freshness. Entertainment or reach must never override safety, truth, or privacy.

The user is the source of community life; operators and businesses are sources of services; VibeMat supplies the shared discovery and connection environment. Users control their own travel logs and sharing choices. Providers control their own business activity and authorised integrations.

### Commercial boundary and current decision

The existing non-negotiable boundary remains in force: VibeMat does not collect, hold, escrow, settle, or distribute passenger fares or provider payments. It may direct a user to a provider's authorised booking/payment channel and may later offer separately scoped commercial tools, subscriptions, advertising, qualified-enquiry services, or attribution products. Any change to payment custody requires a new explicit product and legal decision; it is not implied by consolidating business models.

The marketplace is a product direction, not a claim that every provider has joined or that every service is bookable. Provider onboarding, partnership permissions, API access, booking rights, commercial terms, regulatory obligations, and transaction attribution must be established individually.
