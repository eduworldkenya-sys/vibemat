# Ken's 5:00 AM Decision Experience

**Status:** Product requirement for the passenger experience; exact data sources and first-release scope remain open.

## Scenario

Ken lives in Babadogo near Eastmar Stage. Allsops and Drive-In are also nearby. He commonly travels toward Industrial Area and town, but his destination and travel needs may vary.

At 5:00 AM, Ken opens VibeMat while still at home. He is not necessarily ready to leave and has not yet chosen a stage, route, or exact departure time.

## The problem VibeMat must solve

Ken already knows the nearby stages and can walk to them. A map that only tells him where Eastmar, Allsops, and Drive-In are does not justify opening another app.

VibeMat should reduce the uncertainty he faces before leaving by bringing together transport activity and contextual information that would otherwise require separate enquiries or physically visiting a stage.

## The passenger's questions

1. What transport activity is happening or planned around my nearby stages?
2. Which journeys or departures are declared for the time I may travel?
3. Which providers have explicitly said they are accepting passengers or requests?
4. What is known about stage activity, and how recent is that information?
5. Are there route disruptions, traffic reports, or useful alternatives?
6. Is there weather information relevant to the journey?
7. What has changed since I last checked?
8. What is known, what is uncertain, and what should I verify?

## Proposed screen experience

The map remains the primary screen. A compact, dismissible morning briefing overlays it.

### 1. Map context

Show Ken's current or selected area, nearby stages, relevant roads, and transport activity. Use location only with appropriate permission. Do not reveal his home location to operators or other users.

### 2. Nearby stage comparison

Show Eastmar, Allsops, and Drive-In as mapped places. Where data exists, provide comparable recent activity:
- Recent operator or stage declarations.
- Reported or verified vehicle presence.
- Declared departure windows.
- Explicit availability or capacity.
- Last update time and source.

Do not rank a stage as “best” merely because it has more unverified reports.

### 3. Journey and departure discovery

Show relevant planned journeys and declared departure windows. Make clear whether a departure is operator-declared, partner-supplied, reported by a user, or independently verified.

A planned departure is not a guaranteed departure. “Available” means the provider explicitly declared availability and the declaration is still within its validity period; it does not guarantee a seat.

### 4. Road and weather context

Show traffic, road incidents, road conditions, or weather only when a source is available and its timestamp/freshness can be shown. If no source is available, do not manufacture an insight.

### 5. Changes and discoveries

Surface meaningful changes since Ken last checked, but only when the system has enough reliable history to establish that a change occurred.

### 6. User control

Ken can dismiss the briefing, inspect an item, change the selected destination or time, move the map, or explore other areas. Personalisation must not trap him inside his home area or usual commute.

## Status language and evidence rules

| What the interface says | Minimum meaning |
|---|---|
| Stage mapped | The stage's location is in the map dataset |
| Operator associated | An identified operator declares an association with the stage |
| Reported at stage | A source recently reported the vehicle at the stage |
| Verified at stage | A defined verification method supports current presence |
| Accepting passengers/requests | Provider explicitly declared this, and the declaration has not expired |
| Planned departure | Provider or authorised source declared an intended departure |
| Departed / moving | Fresh live evidence supports the movement claim |
| Historical activity | Past activity; never presented as current |

The exact verification methods and expiry windows remain open.

## Offline behaviour

If Ken is offline, the app may show cached maps and previously retrieved activity if available. Every cached time-sensitive item must show its last-updated time and must not be described as live or current. Actions that require live confirmation should be unavailable or clearly marked as requiring a connection.

## What success means

The experience succeeds if Ken can make a more informed decision before walking to a stage:
- Decide when to leave.
- Choose which stage to inspect.
- Compare declared journeys or route options.
- Identify a disruption or uncertainty.
- Know what still needs direct confirmation.

It does not promise a guaranteed vehicle, seat, fare, departure, or journey time.

## Product hypotheses to test

- A pre-departure briefing is useful enough for passengers to open before leaving home.
- Comparing nearby stages saves unnecessary walking or enquiry.
- Declared journey activity adds value beyond static stage directories.
- Source and freshness labels help passengers judge reliability.

These are hypotheses, not proven outcomes. Pilot research must test them.

## Open decisions

- Which one decision is the first release optimised to help Ken make?
- What is the minimum data needed for a meaningful comparison of nearby stages?
- Which operators or stage agents can publish activity?
- How is publisher identity verified?
- What expiry period applies to a stage report or availability declaration?
- Which traffic, road, and weather sources are acceptable?
- What destination/time input should Ken provide, if any?
- What information is useful offline?
- How should conflicting reports be reconciled?

## Explicit non-goals

- Do not turn the morning screen into a booking checkout.
- Do not imply VibeMat controls the stage or dispatches vehicles.
- Do not treat all map markers as live vehicles.
- Do not show historical reports as current.
- Do not expose Ken's home location.
- Do not invent traffic, weather, fare, or availability data.
