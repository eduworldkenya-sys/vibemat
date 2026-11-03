# Product Architecture

## Agreed architecture: three connected foundations

The architecture serves **Everyone Moves**. Participants share one mobility network but do not all need the same home screen or workflow. The living map is a major shared spatial interface; role-aware discovery and operational surfaces may be more appropriate for particular tasks.

### 1. Living interactive map

The map is a core spatial interface—not the whole product identity and not a mandatory starting screen for every role.

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


## Everyone Moves: shared network, role-aware experiences

VibeMat is not organised around a single passenger persona. It serves the full mobility ecosystem through role-aware experiences over shared data, discovery, trust, and connection foundations.

Participant groups include people travelling; drivers, riders, and conductors; transport operators, SACCOs, and fleet owners; taxi, bus, boda, and rental businesses; delivery, courier, cargo, and logistics providers; travel and experience businesses; and community contributors.

A person may hold multiple roles. Identity and permissions must support multiple authorised roles without creating disconnected products. Each role sees relevant actions and information according to its authority. A passenger's view does not grant operator control; a provider profile does not prove service availability; and a contributor role does not grant access to private movement data.

The product should be evaluated across participant value, network effects, data quality, safety, and commercial sustainability. Ken's passenger journey is one test case, not the product's organising centre.

## Confirmed product direction: TikTok-style social discovery and creator ecosystem

VibeMat will use the **TikTok model as a product and commercial model**, adapted to transport. This is broader than adding a scrolling feed or placing adverts beside moving vehicles. It combines creator/contributor publishing, open recommendation and discovery, following, audience growth, aggregate analytics, business advertising, sponsored distribution, campaigns, and potential creator monetisation.

### Transport-native translation
- Transport activity, updates, explainers, stage reports, route stories, and authorised live updates are the content.
- Kamagers/touts, drivers, conductors, operators, route MCs, and other eligible contributors are publishers/creators, subject to role authority and safety controls.
- The For You-style experience becomes an open transport discovery feed.
- The Following experience surfaces eligible updates from followed contributors, operators, routes, corridors, stages, and activities.
- Views/impressions and follows measure **Attention**; saves and enquiries measure **Intent**; verified boarding, delivery, or service completion measure **Outcome**.
- Creator/business analytics, sponsored discovery, operator campaigns, and future creator earning opportunities form the commercial ecosystem.

The map and feeds are different discovery surfaces over the same underlying transport activity and evidence records. They must not become disconnected content systems.

### Recommendation and trust boundary
Distribution may learn from relevance, explicit interests, follows, freshness, and useful content diversity, but engagement/popularity is not evidence of factual truth. Evidence eligibility, source, timestamp, permissions, freshness, and safety checks happen before distribution. Paid promotion must be visibly labelled and must never buy verification, factual status, or suppression of essential safety information.

A moving vehicle may provide transport context for a route- or area-relevant campaign. It does **not** mean VibeMat can reach or measure every passenger inside that vehicle. Ads reach VibeMat users to whom the content is distributed; onboard passenger reach must not be claimed without a separate, consented and validated mechanism.

### Product boundary
Use the mechanics and staged commercial ecosystem of TikTok, not entertainment-first incentives. Transport usefulness, accuracy, privacy, and user control remain foundational. Do not copy addictive engagement mechanics, reward sensationalism, or let ads obscure transport activity.


## Confirmed strategic thesis: the media network for a world in motion

**Central positioning:** VibeMat is a media, discovery, and advertising network for a world in motion. Its core opportunity is to connect audiences, publishers, businesses, and useful information around human movement—not to own or operate transport assets.

**Everyone moves.** People commute, study, trade, travel, deliver goods, visit family, work, explore, and move between places. Movement creates changing contexts, audiences, needs, and commercial opportunities. VibeMat aims to become a valuable media network where people discover relevant information and businesses reach audiences in those contexts.

### What VibeMat is—and is not
- VibeMat is a media/discovery network and advertising channel focused initially on transport and movement-related contexts.
- It is not a taxi, bus, matatu, logistics, shipping, dispatch, or vehicle-operating company.
- It is not a booking platform or a booking website, and it does not need to compete with existing booking platforms.
- It does not need to own vehicles, roads, petrol stations, garages, shops, fleets, or other physical infrastructure.
- It may connect discovery to an external provider or destination, but that does not make VibeMat the provider or booking/payment intermediary.

### The market is broader than transport operators
Transport is the initial subject matter and entry point, not the limit of the media opportunity. The potential ecosystem includes passengers, commuters, travellers, students, workers, traders, drivers, operators, cargo participants, and businesses that serve people in motion: fuel stations, spare-parts shops, garages, tyre businesses, insurers, restaurants, hotels, retailers, destinations, logistics firms, and other relevant brands.

### Media-network mechanics
VibeMat's value can come from its audience and distribution: useful publishing, discovery, following, creator/contributor reach, contextual advertising, sponsored content, business campaigns, and privacy-safe measurement. Transport activity and movement-related stories are content and context. Businesses can advertise in the network without VibeMat owning their products or services.

The existing map, activity data, intelligence, and discovery foundations remain useful: they provide spatial context and trustworthy movement-related information. They are components of the media network, not evidence that VibeMat must become a transport operator or booking service.

### External social platforms are distribution channels
TikTok, Facebook, YouTube, Instagram, and similar platforms can be used to introduce and popularise VibeMat through marketing, creator content, and links into VibeMat. They are not the competitors VibeMat must defeat, and VibeMat must not depend on them as its own product or audience infrastructure. VibeMat builds and owns its transport/movement-focused network and audience relationship; external platforms can help acquire that audience.

### Strategic success measures
Do not judge the media business only by bookings, vehicles listed, or trips completed. Track relevant reach, active and returning audience, content discovery, follows, publisher participation, advertiser demand, campaign delivery, qualified enquiries, and honestly attributed outcomes. Keep attention, intent, outcomes, and trust evidence distinct. Never claim that a vehicle's passengers saw an advert merely because the vehicle was on a route.

### Pilot boundary
The first real-world pilot remains narrow: online kamagera/touting at one physical Mainstage. It tests whether stage-based transport information and touting can gain useful online discovery and connections. It is a seed for participation and audience—not a launch of a booking platform, a broad ad network, or full creator monetisation.

