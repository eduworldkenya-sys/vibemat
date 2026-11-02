# Discovery and Transport Intelligence

## Purpose

The intelligence layer helps VibeMat understand transport information, identify relationships and patterns, and support discovery without requiring users to know exactly what to search for.

This is broader than sorting a list of vehicles. Ranking is one part of discovery; intelligence also interprets movement, route overlap, stage activity, demand/capacity signals, and changes over time.

## Four connected responsibilities

- **Data:** records what has been declared, reported, observed, verified, or stored historically. It answers: “What information do we have?”
- **Intelligence:** interprets that information to identify meaning, patterns, relationships, confidence, relevance, and possible implications. It answers: “What does this information suggest?”
- **Discovery:** selects which activities or insights to surface to which users, in what order and context. It answers: “What should this person be shown now?”
- **Map:** provides the spatial interface to see, navigate, inspect, and explore the transport network. It answers: “Where is this happening, and what can I explore?”

The data engine is the foundation. Intelligence interprets the data. Discovery distributes findings. The map makes the network explorable.

## Discovery examples

### Route overlap

A driver declares a Nairobi-to-Nakuru journey with cargo capacity. A trader in Nairobi needs a parcel delivered to Nakuru. VibeMat may identify the overlapping journey and surface it as a possible connection.

This is a discovery or matching signal, not a guarantee that the operator will accept the parcel or that the journey will happen.

### Full journey

An operator declares a Nairobi-to-Nanyuki journey but reports that the vehicle is full. The activity can still contribute to movement discovery and historical patterns, while being excluded from available-capacity results.

### Unrequested transport discovery

Ken opens the map and sees a lorry passing through Babadogo, even though he did not search for lorries. This is a transport discovery event, not automatically a recommendation or offer.

## Potential intelligence capabilities

- Nearby activity discovery.
- Route and journey overlap detection.
- Stage activity summaries.
- Transport corridor patterns.
- Movement heatmaps.
- Demand patterns where sufficient evidence exists.
- Capacity discovery.
- Departure and frequency patterns.
- Personal travel trends.
- Historical transport intelligence.
- Cross-location and national discovery.
- Change detection across time when comparable history exists.
- Evidence and confidence interpretation.

These are capability candidates. They should not be represented as already operational.

## Personalisation and exploration

Personalisation can prioritise activity based on a user's location, travel patterns, followed routes, and expressed interests. It must not geographically confine the user.

Ken should be able to explore other parts of Nairobi, other counties, and eventually other supported regions.

If Ken has not specified a destination, VibeMat must not pretend to know which departure is best for that destination. It can present a balanced nearby discovery view, use preferences Ken has explicitly provided, and invite optional refinement.

## Evidence and eligibility before ranking

Discovery must first determine what an item is eligible to claim and where it may appear. Ranking must never make weak or stale evidence look trustworthy.

Before an item can appear in a time-sensitive category:
1. Check its lifecycle status: planned, updated, withdrawn, departed, completed, expired, or historical, as applicable.
2. Check its source and evidence type.
3. Check its timestamp and validity/freshness for that data type.
4. Check for contradictions, duplicates, or superseding updates.
5. Check permissions and visibility rules.
6. Restrict the claim to what the evidence supports.

For example, an expired availability declaration must not appear as currently available. A planned departure may appear as planned, not guaranteed. A user report must not be labelled independently verified. Historical activity may inform patterns but must not appear as live movement.

Items that fail a live/current eligibility check may still be shown in an appropriately labelled reported, stale, or historical context if that is useful and safe. They must not be promoted as current availability or verified live activity.

## Proposed discovery ranking model

After eligibility and evidence checks, discovery can rank eligible items using a context-sensitive model:

1. **User relevance:** fit with the user's current map area, time window, stated destination, followed routes, and explicit preferences.
2. **Evidence quality and freshness:** source reliability, verification level, recency, and consistency.
3. **Activity and discovery value:** meaningful new activity, useful diversity, route overlap, or a pattern that may help the user explore.

The ordering above is a proposed priority, not an approved numeric formula. No fixed 50/35/15 weights have been approved. Activity volume should not automatically win: a crowded stage with many weak reports must not outrank a useful, credible journey merely because it has more markers.

When the destination is unknown, use nearby/time relevance and a balanced mix of activity types rather than inventing destination relevance. Preserve map exploration so personalisation does not trap users in a narrow feed.

The system should be able to explain why an item appeared, for example:
- “Near your selected area.”
- “Declared departure within your chosen time window.”
- “Matches a route you follow.”
- “Recently updated by the operator.”
- “Possible route overlap with your selected journey.”

Only show an explanation that is supported by the actual data and logic.

## Trust and evidence

Every insight should be grounded in available evidence and identify its nature where material:
- Operator-declared.
- User-reported.
- Partner-supplied.
- Sensor or location-derived.
- Independently verified.
- Aggregated historical pattern.
- Estimated or inferred.

The system must not label a declaration as independently verified. Estimates must not be displayed as exact facts. Time-sensitive items should show source, publish/update time, and an appropriate freshness or expiry state.

## Intelligence outputs versus guarantees

A possible route match is not a confirmed booking. A predicted departure is not a guaranteed departure. A heatmap is not proof of an individual vehicle's current position. A demand pattern is not a promise of customers.

## Morning briefing and decision intelligence

A possible first intelligence experience is a short morning briefing for Ken. It should not be a generic feed. It should answer practical questions using the best available evidence for his selected time and area.

Potential briefing components:
- Nearby stage activity summaries with source and update time.
- Planned departures and declared journey windows.
- Explicit availability or capacity declarations.
- Relevant route conditions, traffic reports, and disruptions.
- Weather context when sourced.
- Alternatives and route overlaps relevant to his destination.
- Changes since his last visit, where the system has enough history to support that comparison.

Rank information by usefulness and confidence, not merely by how many markers exist. Do not generate a “best option” where evidence is too weak. Show uncertainty and let Ken inspect the evidence.

## First intelligence use case

**Proposed:** compare activity across Ken's nearby stages and surface relevant planned transport before he leaves home.

This is not yet a verified capability. It depends on obtaining sufficiently fresh and trustworthy stage/operator activity data. Without those sources, the interface must state the limitation.

## Open questions

- What minimum evidence is needed before showing a route match?
- What freshness/expiry rules should apply to each activity type?
- How should confidence and freshness be displayed?
- How should duplicate or contradictory reports be reconciled?
- Which insights should be public, personalised, or restricted?
- What thresholds are required before publishing aggregated trends?
- How should ranking be evaluated with real passenger behaviour before any numeric weights are fixed?

## Two simultaneous modes: open discovery and relevant opportunities

**Agreed product direction:** Ken's daytime dashboard should do both:
1. Keep open discovery of the wider transport network available, even when Ken has not searched or expressed a specific need.
2. Proactively surface transport activities, journeys, capacity declarations, route matches, and insights that may be relevant to Ken's known context or interests, even when he is not currently travelling.

These are not competing feeds and neither should replace the other.

### Open network discovery

- Let Ken explore transport activity across the map and beyond his immediate neighbourhood.
- Include different transport types and activity categories, not only the modes he usually uses.
- Surface meaningful new activity and patterns without requiring a search.
- Preserve user control: Ken can pan, zoom, change layers, search, and explore elsewhere.
- Do not let personalisation hide the wider transport network.

### Relevant opportunity discovery

- Identify published journeys that overlap with routes or places Ken follows or has expressed interest in.
- Surface declared passenger or cargo capacity where relevant and still valid.
- Identify possible route, journey, or location matches.
- Show future departures and planned journeys that may matter to Ken.
- Surface useful transport changes or disruptions affecting saved routes or areas.
- Explain why each item is being shown and identify its source, status, timestamp, and freshness.

An opportunity is a potentially useful discovery, not a confirmed booking, guaranteed seat, guaranteed departure, or promise that an operator will accept a request.

### How the two modes coexist during the day

At 10 AM and 2 PM, the dashboard should not become a passive entertainment feed or a narrow commute-only screen. It should combine:
- A personalised layer of potentially relevant transport opportunities and insights.
- An open discovery layer showing wider transport activity and allowing exploration beyond Ken's usual routes.

The balance can adapt to context and available evidence. Relevant opportunities may be prioritised, but open discovery must remain accessible and visible. If no credible relevant opportunity exists, do not manufacture one; let open discovery carry the experience.

This dual-mode principle can also apply at other times of day. The emphasis changes with Ken's context, but both capabilities remain part of the same transport network.

**Status:** Both open network discovery and proactive relevant-opportunity discovery are agreed product requirements. Exact screen layout, ranking weights, and distribution thresholds remain open.


## Social discovery: following sources without closing the network

VibeMat's social layer is a transport-information network, not an entertainment feed. The content consists of transport declarations, reports, verified updates, corrections, and useful observations.

The same activity records should power:
- **Map discovery:** where activity is happening and what is happening nearby or elsewhere.
- **Following feed:** new and updated information from sources, routes, stages, corridors, and activities the user follows.
- **Open discovery:** eligible information from the wider network, including sources the user does not follow.

Following personalises distribution; it must not hide the rest of the transport network. Feed ranking must still apply evidence eligibility, freshness, privacy, and safety checks before relevance or engagement signals.

### Recommended account interactions

| Interaction | Product purpose | Trust/ranking treatment |
|---|---|---|
| Follow | Subscribe to a source, operator, route, corridor, stage, or activity | Strong preference signal, not proof of quality |
| Save / pin | Privately keep an item, route, stage, or insight for later | Private intent signal; not public popularity |
| View | Understand aggregate reach and whether an item was seen | Analytics only; not proof or a ranking shortcut |
| Confirm | Independently report that an item appears accurate/current | Evidence input, weighted by independence and source quality |
| Dispute / mark outdated | Signal a possible contradiction or stale item | Triggers review/requalification; not automatic proof it is false |
| Report | Flag abuse, fraud, danger, or policy violations | Safety/moderation workflow |
| Share | Distribute an item while retaining its original source, timestamp, and status | Reach signal only; never upgrades credibility |

Do not copy TikTok's engagement mechanics wholesale. Generic likes, follower counts, view counts, and popularity contests should not become the trust model. If a lightweight positive reaction is later introduced, it must be clearly separated from factual confirmation.

### Source reliability and post credibility

Keep three concepts separate:
1. **Source reliability:** the historical quality and accuracy of a contributor's information across eligible posts.
2. **Post credibility:** the evidence supporting this specific declaration or report.
3. **Community feedback:** independent confirmations, disputes, corrections, and reports about the specific item.

A source with many followers or views is not automatically reliable. A popular post is not automatically true. One disputed post should not automatically destroy a source's reputation. Feedback should be checked for independence, coordinated abuse, recency, and corroboration before changing trust assessments.

## Vehicle movement evidence boundary

A moving passenger phone is not a vehicle movement source. A matatu passenger's phone can move exactly as the vehicle moves, but it does not prove that the matatu itself is moving or identify which vehicle it is in.

Only an explicitly authorised vehicle-associated device/source may support a live vehicle movement claim. The source must be linked to that vehicle and enabled under the owner's/operator's sharing choice. Passenger phones must not be silently repurposed as vehicle trackers.

## Stage waiting estimates and aggregation

A stage waiting estimate is a different intelligence signal from vehicle presence or movement. It may be shown only as an approximate, anonymous aggregate when a privacy-reviewed minimum group threshold and bounded time window are satisfied.

Never expose or infer individual identity, coordinates, device IDs, arrival time, or waiting duration. Do not equate stationary phones with waiting passengers or raw device count with people count. Suppress the estimate when the group is too small, evidence is weak, or the estimate is stale. Label any displayed count as approximate and show its time window/freshness.

The minimum threshold, time window, estimation method, and retention policy remain open pending privacy review. This capability is a design candidate, not an implemented feature.


## Road Pulse evidence and predictive routing

Road Pulse contributes time-bounded, direction-aware observations to transport intelligence. The engine must cluster correlated reports (for example, several passengers on the same bus) and distinguish them from independent observations made by another vehicle travelling in the opposite direction. Correlated reports may add witness detail, but must not be counted as fully independent sources.

The five-minute rule is an observation-freshness window, not an automatic incident-resolution timer. When the last fresh observation expires, mark the road state stale/unconfirmed unless new evidence arrives. Never infer that an accident has cleared solely because five minutes passed. A smooth-flow report does not cancel an accident report unless it is relevant to the same segment/direction and the incident's status is independently reassessed.

Normal routing uses the known network. Predictive routing estimates likely journey conditions using appropriately sourced live reports, time-dependent patterns, and available transport declarations. Prediction outputs must include uncertainty, source/freshness context, and an honest unavailable state when evidence is insufficient.

Video, photos, voice, and text can support evidence assessment, but media duplication is not independent corroboration. Machine-detected events are candidate observations until validated by the applicable evidence policy.
