# Map and Interface

## Primary interface decision

**Agreed:** The living interactive map is the main app canvas. It is not a small map card inside a conventional dashboard.

The map is the product's spatial interface. Intelligence and discovery operate through it and through supporting detail views.

## Map responsibilities

The map should support:
- Pan and zoom.
- Place, route, stage, and transport activity search.
- Transport activity markers.
- Stage and location markers.
- Route and corridor exploration.
- Map layer controls.
- Locate-me control.
- Tap-to-inspect activity details.
- Compact floating discovery and intelligence cards.
- Expanded detail panels and navigation to deeper discovery/insight views.
- Open exploration beyond the user's current location and usual routes.

## What the map shows

**Agreed:** Show eligible transport activity across the visible map, not only items personalised to Ken. Highlight relevant opportunities and insights without suppressing open network discovery.

The map may represent:
- Public mapped stages and places.
- Published journeys and planned departures.
- Credibly reported vehicle or transport activity.
- Authorised live GPS positions.
- Approximate activity areas.
- Routes and corridors.
- Aggregated historical patterns.
- Relevant road or traffic reports where sourced.

Not every category will always have data. Omit unsupported information rather than inventing it.

## Marker meaning and evidence

Markers must communicate what they represent. Distinguish stages, declared journeys, community/operator reports, verified presence, authorised live positions, parked/stationary states, stale or unknown states, and aggregated historical activity.

Do not use one visual treatment for all marker types. Colour or icon alone must not be the only way to communicate status. Provide a clear legend and accessible labels.

A route line must not imply a live vehicle journey unless fresh live-position evidence supports that claim.

## Floating information

Small discovery cards may float over the map. They should be:
- Dismissible and expandable.
- Relevant to the visible map area or discovery context.
- Clear about why an item is highlighted.
- Compact enough to preserve map visibility.
- Free of unsupported claims and decorative noise.

Detailed information belongs in an expandable panel or dedicated screen, not in a wall of cards covering the map.

## Proposed bottom navigation

**Recommended default:** Map · Discover · Insights · Profile.

Settings can live inside Profile. This is a product recommendation, not a user-confirmed final navigation decision.

## Example interactions

- Tap a lorry marker → inspect the relevant activity, location precision, source, and time.
- Tap a stage marker → inspect stage identity, recent reports, declared departures, availability declarations, and freshness.
- Tap a journey → inspect publisher, origin/destination, planned time, capacity if declared, status, and next action if enabled.
- Tap a route → explore route information and appropriately labelled history.
- Tap an operator → inspect the operator profile and published activity.
- Tap a heatmap/aggregated area → inspect what period and evidence the pattern represents.

## Visual and interaction direction

- Premium, clean, mobile-first experience.
- High contrast, readable typography, clear hierarchy, generous spacing, and obvious primary actions.
- Map remains visually dominant.
- Consistent visual language and restrained colours.
- Fast, lightweight experience on ordinary mobile networks and lower-end devices.
- Large, accessible touch targets.
- Clear loading, empty, error, offline, and saved states.
- Avoid excessive gradients, random colours, oversized cards, unnecessary emoji, cramped layouts, and generic AI-dashboard styling.
- Never use visual polish to imply data confidence that does not exist.

## Offline and low-data behaviour

Cached maps and activity may remain visible when available, with a prominent last-updated time. Cached information must never be labelled live/current. Do not imply a vehicle is still at its last known position. Actions requiring a network confirmation must be disabled or clearly qualified.

## Open design decisions

- Map provider, licensing, and offline map rights.
- Final marker shapes, iconography, and visual legend.
- Final bottom navigation confirmation.
- Exact map layer categories and controls.
- Per-data-type freshness and expiry thresholds.
- Detailed accessibility and low-data performance requirements.
