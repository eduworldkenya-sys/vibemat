# Map and Interface

## Primary interface decision

The living interactive map is the main app canvas. It is not a small map card inside a conventional dashboard.

## Map responsibilities

The map should support:
- Pan and zoom.
- Place and route search.
- Transport activity markers.
- Stage and location markers.
- Route and corridor exploration.
- Map layer controls.
- Locate-me control.
- Zoom controls.
- Tap-to-inspect activity details.
- Floating discovery and intelligence cards.
- Navigation to deeper discovery and insight views.

## Marker meaning

Markers must communicate what they represent. A marker might represent a stage, declared journey, reported vehicle, verified live position, route, or aggregated activity area.

Do not use the same visual treatment for all of these if it would cause users to confuse their meaning.

## Floating information

Small discovery cards may float over the map. They should be:
- Dismissible.
- Expandable.
- Relevant to the visible map area or the user's discovery context.
- Compact enough to preserve map visibility.

Detailed information belongs in an expandable panel or a dedicated screen, not in a wall of cards covering the map.

## Proposed bottom navigation

**Proposed:** Map · Discover · Insights · Profile

Settings may live inside Profile. This navigation is a design proposal and should be confirmed before implementation.

## Example interactions

- Tap a lorry marker → inspect the relevant activity and its source/time.
- Tap a stage marker → inspect stage activity and freshness.
- Tap a route → explore route information and appropriately labelled history.
- Tap an operator → inspect the operator profile and published activity.

## Design direction

- Premium, clean mobile experience.
- Map remains visually dominant.
- Clear hierarchy and restrained colours.
- Avoid excessive gradients, random colours, oversized cards, unnecessary emoji, and generic AI-dashboard styling.
- Controls should be placed consistently and be easy to use on mobile.

## Open decisions

- Map provider and licensing.
- Exact marker system and visual legend.
- Bottom navigation confirmation.
- Map layer categories.
- Offline map and cached-data behaviour.
- How to represent low-confidence or stale activity.

## Map-first morning experience

The map remains the main canvas when Ken opens VibeMat at 5:00 AM. A compact morning summary may sit over the map, but it must not turn the screen into a dashboard or obscure the surrounding transport context.

The map may show:
- Nearby stages such as Eastmar, Allsops, and Drive-In.
- Declared journeys and departure windows.
- Transport activity with a clear status and source.
- Reported disruptions or traffic conditions when supported.
- Relevant route and corridor context.

A stage marker should open a detail view that distinguishes stage identity, recent reports, verified presence, declared availability, and departures. A route line must not imply a live vehicle journey unless it is supported by live location data.

The user should be able to dismiss or collapse the briefing and continue exploring the map. The interface should make stale or offline information visibly different from fresh information.
