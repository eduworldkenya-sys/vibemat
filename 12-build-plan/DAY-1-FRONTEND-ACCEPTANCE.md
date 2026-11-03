# VibeMat Day 1 Frontend Acceptance

**Date:** 2026-11-03  
**Target:** Complete the pilot frontend experience by end of day.  
**Implementation branch:** `feat/mobile-frontend-day1`  
**Status:** Initial mobile shell committed; completion remains unverified pending installation, launch, screen-by-screen QA, and fixes.

## Required screens

- [ ] Home: For You, Following, Nearby, Trending feed states; short-video post presentation; creator identity; follow, like, comment, share, save affordances.
- [ ] Pulse: road and movement update list; source, time, status, freshness, evidence and correction entry points.
- [ ] Explore: search; map canvas; place, route, stage, corridor and community discovery; map-to-content entry points.
- [ ] Create: short video, photo, text and road update flows; device media picker; caption; preview; visibility and location controls.
- [ ] Communities: discovery, preview, join/leave, community detail, posts and discussion entry points.
- [ ] Inbox: conversation list, message thread, message composer, message request and empty states.
- [ ] Notifications: activity centre, grouped incident alerts, read/unread states and notification preferences entry point.
- [ ] Profile: personal profile, creator/business page entry points, posts, saved items, follows, settings and privacy.
- [ ] Provider discovery: transport and service directory, provider profile, operating-area and self-declared availability presentation.
- [ ] Incident detail: report source, time, status, evidence, confirmations/disputes, update and expiry context.

## Frontend behaviour requirements

- All navigation and controls must respond; no dead buttons.
- Local UI-only state must be clearly separated from server-backed state.
- Media picker permission granted, denied and cancelled states must be handled.
- Search and filter controls must update the visible UI.
- Feed actions, place follows, community joins, create flow, inbox, and notifications need explicit empty/loading/error states.
- Responsive layouts and accessible touch targets must be checked at small and large phone sizes.
- Use the VibeMat visual direction: premium, restrained, high contrast, dark ink / warm neutral surfaces / restrained gold accent; no green-dominant theme or noisy gradient-heavy dashboard.

## Honest mock-data boundary

Fixtures are permitted for Day 1 layout and interaction development, but must be visibly treated as sample content. Never present fixture reports as live incidents, fixture markers as real vehicle positions, or placeholder listings as verified providers. No action may claim a successful upload, publish, message, follow sync, notification delivery, or incident submission before backend integration confirms it.

## Completion evidence required before marking Day 1 complete

1. Dependency installation succeeds.
2. TypeScript check succeeds.
3. Expo app launches successfully.
4. Screens and navigation are exercised on Android and iOS simulator/device or documented supported test environments.
5. Media permission states and responsive layouts are checked.
6. All visible controls are tested; broken or misleading interactions are fixed.
7. Known limitations are listed in the PR and repository.

The current initial implementation is not yet certified against these checks. Day 2 backend integration must not be used to conceal missing Day 1 screens or broken frontend navigation.
