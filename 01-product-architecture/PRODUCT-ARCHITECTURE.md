# Product Architecture

## Agreed architecture: three connected foundations

### 1. Living interactive map

The map is the actual app canvas and primary interface—not a small card embedded in a dashboard.

It allows a person to:
- Pan and zoom across places.
- Explore roads, stages, locations, corridors, and routes.
- See transport activity represented spatially.
- Tap markers to inspect the underlying activity.
- Explore activity nearby or deliberately move to another area.

The map can show different kinds of transport and activity. It should not imply that every marker is a vehicle currently moving.

### 2. Transport intelligence and discovery algorithm

This layer interprets the underlying data and decides what may be useful to surface.

Potential responsibilities:
- Rank relevant discoveries.
- Identify route overlap and possible journey matches.
- Recognise stage and corridor activity.
- Aggregate movement patterns and heatmaps.
- Identify demand and capacity signals where data supports them.
- Build personal travel trends.
- Distinguish current, planned, reported, and historical activity.
- Support discovery across the map, not only near the user's current location.

The algorithm is a product capability, not a claim that every insight will be available at launch.

### 3. Underlying data engine

This is the foundation that makes the map and intelligence meaningful. It stores and governs records such as:
- People and participant roles.
- Operators, vehicles, and transport modes.
- Places, stages, roads, routes, and corridors.
- Transport activities and journey declarations.
- Origin, destination, departure, and status.
- Capacity and availability declarations.
- Commercial intent where relevant.
- Media and updates.
- Source, timestamp, freshness, and verification state.
- Permissions, privacy settings, and visibility.
- Historical records and aggregation eligibility.

## How the layers work together

1. A participant or trusted source declares or reports transport activity.
2. The data engine stores the activity with its source, time, status, and permissions.
3. The map presents the activity in its appropriate spatial and temporal context.
4. The intelligence layer evaluates relevance, overlap, patterns, and possible connections.
5. The user discovers an item and can inspect its details.
6. The activity can be updated, completed, withdrawn, or retained as appropriately labelled history.

## Core domain distinction

The core unit should be **transport activity**, not only a static vehicle or route listing. A vehicle, route, journey, capacity declaration, movement observation, media item, or operator profile may contribute to an activity record.

## Architecture constraints

- Do not treat a planned journey as a live vehicle position.
- Do not treat a historical route as current availability.
- Do not infer that a visible vehicle is accepting customers.
- Do not expose private exact locations by default.
- Do not create separate disconnected apps for each participant type.
- Do not make the map dependent on an unverified claim of real-time tracking.

## Status

**Agreed:** three-part architecture—living map, transport intelligence, and underlying data engine.

**Open:** exact technical architecture, data providers, map provider, tracking mechanisms, and launch infrastructure. These are deliberately not being selected during the product-notes stage.
