# Social Mobility Marketplace

## Product definition

VibeMat is a **social mobility network and consolidated transport marketplace**. It brings transport businesses, services, users, and mobility experiences into one shared environment.

The ambition is not to replace Google Maps, become Uber, or operate every vehicle. VibeMat changes how people discover, experience, share, and connect with transport. The map is one useful interface and an underlying spatial capability; it is not the product's entire identity.

The analogy is a broad social platform that can host many kinds of content and commercial activity without owning every creator or business. VibeMat applies that ecosystem model to mobility.

## Provider and service categories

The marketplace is designed to accommodate independent providers across categories:

| Category | Examples of participants and services |
|---|---|
| Ride-hailing and taxis | Uber, Bolt, independent taxi operators and fleets |
| Intercity and scheduled transport | 2NK, Mololine, coach operators, shuttles and ticketing businesses |
| Public and informal transport | Matatus, SACCOs, city buses and other local operators |
| Two- and three-wheel mobility | Boda boda businesses, motorcycle taxis and tuk-tuks |
| Vehicle access | Car hire, vehicle rental and chauffeur services |
| Travel and experiences | Tours, road trips, travel packages and passenger experiences |
| Delivery and courier | Parcel delivery, last-mile delivery and courier operators |
| Cargo and logistics | Lorries, trucks, cargo owners, freight and moving services |
| Mobility-adjacent services | Other relevant services that help people or goods move |

Named businesses are examples of the intended provider ecosystem. Their appearance in this blueprint does not mean they have partnered with VibeMat, supplied data, authorised an integration, or made inventory available.

## What consolidation means

VibeMat brings these businesses into one discovery and connection environment while preserving their independent identities and business models.

- A passenger can discover different ways to travel without treating each provider as a separate digital world.
- A bus operator can publish routes, trips, schedules, capacity, and service updates.
- A ride-hailing provider can be discovered and, where authorised, connected through its supported service flow.
- A boda operator or local transport business can publish a service area and availability declaration.
- A courier can publish delivery coverage and accept qualified enquiries through an authorised workflow.
- A rental or tour business can present vehicles, packages, availability, and booking instructions.
- Commuters can contribute road observations, dashcam clips, journey stories, and Travel Logs.

The platform should support different business models rather than force every provider into one generic listing or booking model.

## Provider integration levels

Every provider's integration status must be explicit. Possible levels include:

1. **Discoverable profile:** business information and service category, with verified ownership and update controls where available.
2. **Provider-published activity:** routes, schedules, service areas, offers, declared availability, and updates.
3. **Enquiry/contact connection:** a user can initiate an enquiry or continue through a provider-authorised contact channel.
4. **External booking handoff:** VibeMat sends the user to the provider's official booking or checkout flow.
5. **Authorised API integration:** an approved technical connection exposes specified inventory, schedules, booking status, or other data.
6. **Deeper transaction integration:** only if separately authorised, legally reviewed, and explicitly approved as a product decision.

A profile is not proof of current availability. A published trip is not a confirmed seat. A link is not a booking. An API connection must state exactly which data and actions it supports. VibeMat must not imply a partnership or integration without documented permission.

## Independent ownership and accountability

Each provider retains control and responsibility for its:
- Business identity and brand.
- Vehicles, employees, contractors, and operations.
- Routes, service areas, schedules, prices, capacity, and availability declarations.
- Customer terms, fulfilment, cancellations, refunds, and service quality.
- Licences, insurance, regulatory compliance, and customer support.
- Authorised integrations and the data it chooses or is permitted to share.

VibeMat governs platform access, discovery rules, content and information safety, source labelling, privacy, platform integrity, and any services it directly provides. Responsibilities must be contractually clear before a provider is onboarded.

## Social mobility: the user-powered layer

The social experience is not an unrelated entertainment feed. It is how people and providers share useful mobility experiences and information.

Content and activity can include:
- Privacy-protected road-facing dashcam videos.
- Journey stories and user-controlled Travel Logs.
- Road Pulse observations and corrections.
- Route and stage explainers.
- Provider announcements and service updates.
- Vehicle, transport, and travel experiences.
- Useful community discoveries and local mobility information.

A post should retain its source, timestamp, location precision appropriate to the content, status, and freshness. Views, shares, and reactions do not prove that a report is true or that a service is available.

All public media must follow the platform's strict privacy rules: no public exposure of identifiable faces, number plates, sensitive personal information, private passenger interiors, or unprocessed camera footage. If required privacy checks cannot pass, the media must not be published.

## Commercial models VibeMat can accommodate

The platform should not force providers into a single revenue model. Depending on provider type and authorised integration, the ecosystem may accommodate:

- Per-ride or per-trip provider transactions.
- Scheduled bus ticket sales through the provider's authorised channel.
- Delivery and courier fees.
- Cargo/freight quotations and contracts.
- Vehicle rental charges.
- Tour and travel package sales.
- Provider subscriptions for business tools and enhanced presence.
- Clearly labelled advertising and sponsored discovery.
- Qualified enquiries and transparent lead attribution.
- Optional creator or route-explainer campaigns funded by participating businesses.

These are supported marketplace patterns to design for, not confirmed revenue streams, signed customers, or approved prices. Sponsored placement must never buy verification, favourable factual status, or guaranteed ranking.

## Payment boundary

The current confirmed product rule remains: **VibeMat does not collect, hold, escrow, settle, or distribute passenger fares or provider payments.**

Where supported, a user may continue to a provider's authorised app, website, ticketing system, or payment channel. Any future VibeMat-operated checkout, wallet, payment custody, settlement, or commission deducted from provider funds would require a separate explicit decision, technical design, and legal/regulatory review. Consolidating business models does not silently authorise VibeMat to handle money.

## Trust, freshness, and availability

The platform must distinguish:
- Business profile from verified business identity.
- Provider-published schedule from live operational status.
- Declared availability from confirmed inventory.
- Enquiry from booking.
- Booking from completed fulfilment.
- User report from independently verified observation.
- Sponsored content from organic discovery.
- Historical content from current information.

Each dynamic claim should carry a source and timestamp. Expired or unconfirmed information must be labelled accordingly. Discovery ranking must not allow payment or popularity to masquerade as trust.

## Product architecture implications

The consolidated marketplace extends the existing VibeMat foundations:

- **Data engine:** providers, business profiles, service categories, offerings, schedules, capacity declarations, integrations, enquiries, and outcome records.
- **Transport intelligence:** relevance, route/service matching, provider comparison, demand signals, and aggregate insights.
- **Discovery:** map, feed, search, category browsing, followed providers, and contextual recommendations.
- **Connection layer:** contact, enquiry, external handoff, and explicitly authorised APIs.
- **Social layer:** user and provider publishing, journey stories, Road Pulse, Travel Logs, and privacy-protected media.
- **Governance:** provider verification, permissions, content moderation, privacy, commercial disclosures, audit history, and dispute handling.

These are product capabilities. They do not authorise implementation or claim provider integrations exist.

## Decisions and open questions

### Confirmed direction
- VibeMat is a social mobility network, not a Google Maps replacement or a single transport operator.
- Multiple independent transport businesses and service categories should be consolidated into one discovery and connection ecosystem.
- Providers retain their identities, business models, operational control, and customer responsibilities.
- Users and providers create the activity and experiences that make the network valuable.
- Public media must never expose identifiable faces or sensitive personal data.
- The current no-custody payment boundary remains in force.

### Still open
- Which provider categories and participants belong in the first pilot.
- Whether the first pilot uses listings, provider-published activities, enquiries, external booking handoffs, or a limited authorised API.
- Provider verification and onboarding requirements by category.
- Data-sharing permissions and commercial/technical agreements with each provider.
- Which service types can be compared and what fields make comparisons fair.
- How booking, cancellation, refunds, and fulfilment status are represented when handled by providers.
- Which commercial model to test first and what evidence will define success.
- Whether any future payment handling is desirable; no such change is currently approved.

## Release principle

Build the shared ecosystem model in the blueprint first. Pilot a narrow, measurable provider mix before claiming marketplace coverage. Never list a business as integrated, available, bookable, or partnered without current evidence and permission.
