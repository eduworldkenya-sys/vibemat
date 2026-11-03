# VibeMat Global, Local and Place-Follow Discovery Decision

**Status:** Product decision confirmed  
**Applies to:** Social feed, recommendations, Explore, Pulse, communities, and notifications  
**Blueprint:** Social Network Product Specification v0.3

## Confirmed decision: users can follow multiple places independently of current location

A VibeMat user may follow multiple places, regions, routes, stages, or communities regardless of where they are physically located.

Example: a user currently in Nairobi may follow Mandera, Mombasa, and Busia at the same time. Relevant public content and updates associated with those places may be included in that user's discovery and notification experiences without changing or misrepresenting the user's current location.

Following a place:
- Does not change the user's physical location.
- Does not imply that the user lives there, comes from there, or intends to travel there.
- Does not automatically make every post from that place appear.
- Does not grant access to private content or bypass creator audience controls.
- Is a relevance preference, not a service subscription or endorsement.

## Discovery principle

**Global discovery. Local intelligence. Connected movement.**

VibeMat must not confine a user to their current county, town, or country. A creator in Peru may trend among users in Kenya when their content is relevant and engaging. Equally, a user in Mandera should be able to discover global creators, national transport developments, local Mandera content, and information from places they deliberately follow.

Location improves relevance; it must not limit discovery.

## Five recommendation dimensions

The recommendation system should consider these dimensions together, with dynamic ranking rather than fixed permanent feed quotas:

1. **Interest:** topics, formats, creators, and content the user chooses to engage with.
2. **Social relationships:** followed people, pages, vehicles, routes, places, and communities.
3. **Current geographic relevance:** local content and events near the user's current area, only where permitted by their location settings.
4. **Movement relevance:** routes, corridors, destinations, stages, and transport topics the user follows or has indicated are relevant.
5. **Industry relevance:** transport news, policy, fuel, safety, infrastructure, weather, and other developments relevant to the user's interests or context.

Safety, privacy, content eligibility, and information-integrity requirements are hard constraints. They must not be outweighed by engagement or popularity.

## Place-follow model

Users should be able to follow multiple geographic and movement entities, including:
- Countries, counties, towns, cities, and neighbourhoods.
- Roads, corridors, and routes.
- Stages, terminals, and transport hubs.
- Location-based communities.
- Other supported public places and transport entities.

The product should distinguish following a place from following a community about that place. A user may follow either or both.

## Distribution and notifications

Place follows may inform:
- For You and other discovery surfaces.
- Explore search and map recommendations.
- Pulse and relevant industry/local updates.
- Notifications for meaningful developments.

A place follow is not permission to send unrestricted alerts. Notification delivery must still apply relevance, severity, freshness, deduplication, frequency limits, user preferences, quiet hours, and channel consent. Ordinary content can be discoverable in-app without automatically generating push or SMS notifications.

Current location and followed places must remain separate data concepts. A user may choose to share current location, follow places without sharing location, or disable location-based personalisation.

## Illustrative scenarios

- A user in Nairobi follows Mandera, Mombasa, and Busia. Relevant public content from all three places can appear in discovery.
- A user in Mandera watches transport culture videos and may discover a creator in Peru through interest-based recommendations.
- A user in Mombasa follows the Nairobi–Mombasa corridor and may receive meaningful updates affecting that route while remaining physically in Mombasa.
- A user who does not follow a place may still receive a high-priority public safety alert if it is genuinely relevant to their current location or journey and their notification settings permit it.

## Implementation status

This is a confirmed product decision and specification requirement. It is not evidence that place-follow functionality, ranking, location processing, push delivery, or SMS delivery has been implemented.
