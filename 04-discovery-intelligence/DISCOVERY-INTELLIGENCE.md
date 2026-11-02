# Discovery and Transport Intelligence

## Purpose

The intelligence layer helps users discover relevant activity and understand transport patterns without requiring them to know exactly what to search for.

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

These are capability candidates. They should not be represented as already operational.

## Personalisation and exploration

Personalisation can prioritise activity based on a user's location, travel patterns, followed routes, and expressed interests. It must not geographically confine the user.

Ken should be able to explore other parts of Nairobi, other counties, and eventually other supported regions.

## Trust and evidence

Every insight should be grounded in available evidence and identify its nature where material:
- Operator-declared.
- User-reported.
- Partner-supplied.
- Sensor or location-derived.
- Independently verified.
- Aggregated historical pattern.
- Estimated or inferred.

The system must not label a declaration as independently verified. Estimates must not be displayed as exact facts.

## Intelligence outputs versus guarantees

A possible route match is not a confirmed booking. A predicted departure is not a guaranteed departure. A heatmap is not proof of an individual vehicle's current position. A demand pattern is not a promise of customers.

## Open questions

- What minimum evidence is needed before showing a route match?
- How should confidence and freshness be displayed?
- How should duplicate or contradictory reports be reconciled?
- Which insights should be public, personalised, or restricted?
- What thresholds are required before publishing aggregated trends?
