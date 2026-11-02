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


## Ken's 5:00 AM map hierarchy

### First screen

The map is the first screen and remains visible. It should show the user's permitted location context, nearby stages, relevant roads, and clearly differentiated transport activity markers. A compact, dismissible morning briefing sits above the map; it must not replace the map with a dashboard.

### Morning briefing priority

1. Relevant declared journeys and departure windows.
2. Explicitly declared passenger availability or capacity.
3. Recent nearby stage activity.
4. Sourced road disruptions or traffic context.
5. Sourced weather context.
6. Meaningful changes since the last visit, if history supports the comparison.

Hide unavailable categories rather than inventing data or displaying misleading zeroes.

### Tap behaviour

**Stage marker:** open a stage detail panel with stage identity/location, activity time window, individual reports, declared departures, explicit availability, relevant road reports, and source/time/freshness labels. Include a clear “no recent reliable activity” state.

**Journey or vehicle marker:** open an activity detail panel with publisher, origin/destination, declared route, planned time, vehicle type, capacity/availability if declared, status, source, last update, and expiry. Show contact/next action only if the publisher has enabled it.

**Route marker/line:** open route information and appropriately labelled historical patterns. A line must not imply live movement without fresh live-position evidence.

### Overlay versus detail

Map overlays contain only the short decision-relevant summary, status, and freshness. Publisher details, multiple reports, comparisons, and history belong in the expanded panel or Discover/Insights.

### No-data and offline

Do not fabricate activity, counts, rankings, traffic, or weather. When no reliable live data exists, state that recent activity is unavailable while keeping the map usable. Cached data must display its last update and must never be called live/current.

### Visual semantics

Use distinct visual treatments and a visible legend for stages, declared journeys, user/operator reports, verified presence, live positions, and aggregated historical activity. Colour or icon alone must not be the only way to communicate status.
