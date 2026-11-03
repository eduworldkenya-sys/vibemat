# VibeMat mobile frontend

Expo + React Native + TypeScript frontend for the Android and iOS consumer app.

## Run locally

```bash
npm install
npx expo start
```

## Day 1 frontend scope

Implemented as the initial mobile UI shell:
- Home feed and For You / Following / Nearby / Trending entry points.
- Pulse overview with incident cards and explicit demo/unverified labelling.
- Explore search, map preview, place-follow controls, and service discovery entry points.
- Create composer with device photo/video library picker.
- Communities discovery and join/leave interaction states.
- Profile surface, Inbox empty state, and five-item bottom navigation.
- Local interaction state for likes, follows, joins, tabs, and feedback.

## Honest integration boundary

The current sample feed and map illustration are fixtures, not live platform data. Backend-dependent actions intentionally show a pending-integration message. Real account/session handling, media upload and playback, feed retrieval, map tiles/geocoding, place-follow persistence, comments, DMs, communities, incident submission, and push notifications are Day 2/3 integration work.

Do not label this frontend complete until dependencies install, TypeScript checks pass, Expo launches, and every screen is exercised on Android/iOS device or simulator sizes.
