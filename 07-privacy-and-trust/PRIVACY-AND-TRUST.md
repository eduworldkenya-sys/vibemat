# Privacy, Trust, and Information Quality

## Core principle

Transport discovery must not require exposing more personal or operational information than is necessary.

## Location privacy

- Do not expose a person's home address by default.
- Do not expose a driver's or vehicle's exact live location unless the participant has knowingly enabled an appropriate sharing mode.
- Use an appropriate level of geographic precision for public discovery.
- Distinguish a public stage or route from a private origin or destination.
- Provide controls for activity visibility and history visibility.

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
- Live position from an identified source.
- Aggregated historical pattern.

The exact trust model remains open. These labels are conceptual categories, not a finished verification policy.

## User control

Participants should be able to understand and control:
- What activity they publish.
- Who can discover it.
- Whether route history is publicly visible.
- Whether exact location is shared.
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

These are required design topics; no completed policy is claimed here.

## Location and morning context safeguards

A morning experience may use a passenger's current or selected area to prioritise nearby information, but it must not reveal their home location to operators or other users by default.

The product should distinguish:
- Private user location used for personal relevance.
- Public mapped stage locations.
- Approximate activity areas.
- Exact vehicle location shared by an operator under an explicit setting.
- Verified live positions supplied by an authorised source.

Cached/offline information must show when it was last updated. A stale report must not be presented as current stage readiness, traffic, weather, or vehicle availability.
