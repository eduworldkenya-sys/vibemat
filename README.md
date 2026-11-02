# VibeMat

**A social mobility network.**  
**Tagline:** As We Move.  
**Product philosophy:** Everyone Moves.

VibeMat connects the people, businesses, services, vehicles, journeys, and communities that participate in movement. It helps them discover, share, understand, and participate in mobility.

## Project status

**Stage:** Product discovery and documentation  
**Current rule:** No application coding or deployment until the product blueprint is sufficiently defined.  
**Source of truth:** This repository.

VibeMat is one connected mobility network—not a passenger app with secondary tools bolted on. People may participate in multiple roles, and role-specific experiences share the same underlying network.

## Product thesis

A person should be able to open VibeMat without already knowing what transport they want to find. The map should reveal relevant transport activity nearby and across places the person chooses to explore. An intelligence layer interprets that activity and helps people discover useful connections, patterns, and opportunities.

## Foundational architecture

1. **Living map:** the primary app canvas for exploring places, roads, stages, routes, vehicles, journeys, and transport activity.
2. **Transport intelligence:** the discovery and decision engine that interprets activity, identifies route overlap, surfaces relevant discoveries, and builds transport insights.
3. **Data engine:** the underlying records, timestamps, sources, trust signals, permissions, and history that make the map and intelligence reliable.

## Product organising principle

**Everyone Moves.** The product is organised around the full mobility ecosystem: people travelling, people operating vehicles, transport businesses, logistics providers, service providers, and community contributors. Ken remains one useful passenger example, not the organising persona or the definition of the product.

## Non-negotiable money boundary

VibeMat will not collect, hold, escrow, settle, or distribute passenger fares or transport payments. Passengers pay transport providers directly through their existing channels. VibeMat may record relevant activity and attribution without handling the money.

## Documentation map

- [Product vision](00-vision/PRODUCT-VISION.md)
- [Product architecture](01-product-architecture/PRODUCT-ARCHITECTURE.md)
- [Ken: passenger experience](02-ken-passenger-experience/KEN-PASSENGER-EXPERIENCE.md)
- [Transport ecosystem and activities](03-transport-ecosystem/TRANSPORT-ACTIVITIES.md)
- [Discovery and intelligence](04-discovery-intelligence/DISCOVERY-INTELLIGENCE.md)
- [Map and interface](05-map-experience/MAP-AND-INTERFACE.md)
- [Business model boundaries](06-business-model/BUSINESS-MODEL.md)
- [Privacy and trust](07-privacy-and-trust/PRIVACY-AND-TRUST.md)
- [Road Pulse, routing, live mobility, and Travel Logs](09-road-pulse-live-mobility/ROAD-PULSE-LIVE-MOBILITY.md)
- [Social mobility marketplace](10-social-mobility-marketplace/MOBILITY-MARKETPLACE.md)
- [Open decisions and backlog](08-open-decisions/OPEN-DECISIONS.md)

## Decision language

- **Agreed** — explicitly established as a product requirement.
- **Proposed** — a candidate idea that still needs a decision.
- **Open** — unresolved; do not silently assume an answer.
- **Rejected** — explicitly ruled out.

New ideas should be documented with their problem, intended behaviour, affected participants, dependencies, conflicts, and decision status. Do not turn an unapproved proposal into an agreed requirement.

## Working method

We are writing and reviewing the product blueprint before building. No HTML prototype, backend, integrations, or deployment work is authorised by this documentation stage.

## Core product test: Everyone Moves

Every major product decision must be tested against the needs and authority of the relevant mobility participants—not only a passenger. At 5:00 AM, before deciding when or how to leave, he can use it to understand nearby transport activity, compare relevant options, inspect declared departures, see road conditions where sourced, and discover useful activity along or beyond his usual routes.

The product must provide decision-support that a walk to Eastmar Stage alone cannot provide. It must not pretend to know live vehicle positions, stage readiness, fares, traffic, or weather without a current and identifiable source.

See [Ken's 5:00 AM decision experience](02-ken-passenger-experience/KEN-5AM-DECISION-EXPERIENCE.md).

## Product identity: the social mobility network

VibeMat is not being built to replace Google Maps or to become a single transport operator. Its ambition is to change how people discover, experience, share, and participate in transport. The map, routing, and location capabilities are infrastructure serving that experience—not the whole product identity.

The product combines a living mobility network with social discovery and a multi-provider commercial marketplace. Users and independent businesses bring the activity, services, stories, and supply. VibeMat connects them through shared discovery, trusted information, and provider-authorised service journeys.

See [Social mobility marketplace](10-social-mobility-marketplace/MOBILITY-MARKETPLACE.md) for the provider categories, business models, integration boundaries, and commercial principles.
