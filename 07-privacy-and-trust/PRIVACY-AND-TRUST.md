# Privacy, Trust, and Information Quality

## Core principle

Transport discovery must not require exposing more personal or operational information than is necessary.

VibeMat should make useful transport activity discoverable without turning every participant, vehicle, or journey into a permanently trackable public target.

## Public visibility versus precise tracking

A vehicle travelling on a public road can ordinarily be seen by people nearby. VibeMat may make relevant, deliberately published or credibly observed public transport activity discoverable. This does not mean every vehicle must broadcast its exact GPS coordinates or expose a continuous movement trail.

Keep these concepts separate:
- **Publicly observable activity:** a vehicle or transport activity that can be seen in a public place or has been deliberately published for discovery.
- **Approximate location:** a general area or map position that does not expose precise coordinates.
- **Exact GPS position:** precise coordinates supplied by a device or authorised source.
- **Continuous tracking/history:** a sequence of positions over time, which can reveal routines, routes, stops, and sensitive patterns.

Public visibility at one moment is not blanket permission for continuous tracking or permanent publication of a movement history.

## GPS and operator control

GPS may be used as a source for vehicle location when the relevant operator or authorised participant has enabled and consented to that sharing mode.

The proposed operator-controlled modes are:
- Approximate location.
- Exact live GPS location.
- No GPS location sharing.

Exact live location must not be public by default. The operator must be able to understand and control when precise tracking is active, who can see it, and when sharing stops. Any authorised operational or safety access must be governed by a separately defined policy and lawful authority; it must not be assumed from public map visibility.

A vehicle can still be discoverable through a published journey, public route/stage information, or a credible observation even when it is not sharing GPS. The interface must identify the source and must not imply GPS verification where none exists.

## Location privacy

- Do not expose a person's home address by default.
- Do not expose a driver's or vehicle's exact live location unless the participant has knowingly enabled an appropriate sharing mode or a separately established lawful/authorised basis applies.
- Use an appropriate level of geographic precision for public discovery.
- Distinguish a public stage or route from a private origin or destination.
- Provide controls for activity visibility and history visibility.
- Treat movement histories and repeated location patterns as sensitive, even when individual sightings occurred in public.

## Source and freshness

Every time-sensitive item should carry enough context to avoid misleading users:
- Who or what supplied the information.
- When it was supplied or observed.
- Whether it is planned, declared, reported, live, estimated, or historical.
- Whether it has been verified.
- Whether it may now be stale.

Historical information must never be presented as live.

## Trust states

The product should be able to distinguish:
- Unverified declaration.
- Community report.
- Partner-supplied information.
- Independently verified information.
- Live GPS position from an identified and authorised source.
- Aggregated historical pattern.

The exact trust model remains open. These labels are conceptual categories, not a finished verification policy.

## User control

Participants should be able to understand and control:
- What activity they publish.
- Who can discover it.
- Whether route history is publicly visible.
- Whether exact GPS location is shared.
- When GPS sharing is active and when it stops.
- Whether an activity is still active, completed, or withdrawn.

## Safety and abuse questions

Before launch, the product needs policies and workflows for:
- False or misleading journey declarations.
- Impersonation.
- Harassment or unwanted contact.
- Fraudulent capacity or cargo claims.
- Unsafe or prohibited transport activity.
- Reporting, moderation, and dispute handling.
- Data retention and deletion.
- Access to sensitive location and activity history.
- Misuse of GPS access or tracking credentials.

These are required design topics; no completed policy is claimed here.

## Location and morning context safeguards

A morning experience may use a passenger's current or selected area to prioritise nearby information, but it must not reveal their home location to operators or other users by default.

The product should distinguish:
- Private user location used for personal relevance.
- Public mapped stage locations.
- Approximate activity areas.
- Exact vehicle GPS location shared by an operator under an explicit setting.
- Verified live positions supplied by an authorised source.

Cached/offline information must show when it was last updated. A stale report must not be presented as current stage readiness, traffic, weather, or vehicle availability.

## Why VibeMat adds value beyond looking at the road

VibeMat should not pretend that a passenger needs an app to see a vehicle that is already plainly visible on the road. Its value is in connecting information that is difficult to gather by standing at one roadside location:
- Discovering published journeys before reaching a stage.
- Seeing activity across multiple stages, routes, and locations.
- Finding relevant journeys and possible route overlaps.
- Understanding declared availability and planned departures, with evidence and freshness.
- Exploring transport activity beyond what is immediately within sight.
- Seeing useful patterns and changes over time without exposing unnecessary personal or operational detail.

A nearby vehicle sighting can be one useful data point, but the product should provide context and network-wide discovery rather than merely duplicating what Ken can see with his eyes.

## Proposed automatic stationary privacy protection

A vehicle's GPS being enabled must not mean that its precise position remains publicly visible indefinitely.

**Proposed behaviour:**
- When an authorised GPS source detects that a vehicle has remained stationary for a configured period, VibeMat changes its public tracking state to **Parked / Stationary**.
- Public exact-location sharing is automatically suspended.
- The last precise GPS position is not left visible on the public map or exposed as the vehicle's current location.
- The owner or authorised operator can still access the vehicle's exact location in their authenticated account, subject to account permissions.
- The owner/operator may deliberately bring the vehicle's GPS presence online again, including for a short, time-limited sharing session.
- The interface must distinguish parked/stationary, GPS unavailable, tracking paused, and moving. These states must not be conflated.

The stationary timer must use reliable GPS/device evidence and tolerate temporary signal loss or GPS jitter. A lack of updates alone must not be described as proof that a vehicle is parked. If the system cannot determine the state confidently, show an honest unknown/stale state and protect the last precise location from public display.

**Agreed default threshold: 20 minutes.** After reliable stationary detection for 20 minutes, suspend public exact-GPS visibility and do not display the last precise position publicly. The owner/authorised operator can still access exact location in their authenticated account and may deliberately resume public sharing. This is a product rule, not an implemented GPS capability. Category-specific exceptions and temporary-session duration remain open.

This protection is about public exposure of precise location. It does not require deleting the private location record immediately; retention and deletion periods require a separate policy.


## Vehicle movement must not be inferred from passenger phones

A moving phone is not evidence of a moving vehicle. A passenger inside a moving matatu has a moving phone, and the device-motion signal does not establish which vehicle the person is in or whether the vehicle itself is moving.

A public vehicle movement claim requires a fresh source explicitly associated with and authorised for that vehicle, such as the vehicle's own device or a driver/operator device deliberately configured for that vehicle. The owner/operator's selected sharing mode controls whether approximate or exact live location is shared, or whether no GPS is shared.

Passenger devices must not be silently used as vehicle trackers. If the source is a passenger observation, label it as a report and do not upgrade it to verified vehicle movement.

## Stage waiting information: aggregate, anonymous, and bounded

Stage waiting estimates can be useful, but tracking individual waiting passengers is not acceptable product behaviour.

If an estimate such as “approximately 3 people waiting” is ever displayed:
- It must be an aggregate estimate, not a roster or individual trace.
- It must not expose identities, individual coordinates, device identifiers, arrival times, or individual waiting durations.
- It must use a bounded observation window and a minimum group threshold.
- Suppress small groups and weak or stale estimates.
- Label the result as approximate and show its time window/freshness.
- Do not equate phones with people; account for uncertainty, multiple devices, and people without phones.
- A stationary phone near a stage does not establish that its owner is waiting for transport.

The minimum group threshold, time window, estimation method, lawful/consent basis, retention, and deletion rules require privacy review before implementation. If safe aggregation cannot be demonstrated, do not show a count. This is a design constraint, not an implemented capability.

## Social feedback and privacy

Following, saving, viewing, confirming, disputing, and sharing have different meanings and should not be collapsed into a generic engagement score.

- Saved/pinned items are private by default.
- A passenger's followed routes, stages, and contributors must not reveal their home, work, or travel routines publicly by default.
- Individual viewer identities and locations must not be exposed to publishers; provide only appropriately aggregated reach analytics.
- Confirmations and disputes should be attached to the relevant information item, not published as a public list of identifiable passenger witnesses.
- Do not equate follower count, views, shares, or reactions with source reliability or post truth.
- Comments and direct messages are not assumed; any later introduction requires abuse, harassment, privacy, and moderation controls.
