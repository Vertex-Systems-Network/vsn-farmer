# Options: Mobile app approach
- Status: chosen (ADR-0003)
- Related FR: §5, NFR compatibility, SRS Phase 5 Android app

| Option | Impact | PK fit | Cost | Effort | Risk | Total | Notes |
|---|---|---|---|---|---|---|---|
| React Native (Expo) | 5 | 5 | 4 | 4 | 4 | 22 | Same TypeScript as web; share types, API client, translations |
| Flutter | 5 | 5 | 4 | 3 | 4 | 21 | Great on cheap Android, but separate language (Dart) |
| PWA only | 3 | 3 | 5 | 5 | 3 | 19 | No Play Store presence, weaker notifications |
| Native Kotlin/Swift | 5 | 5 | 2 | 1 | 4 | 17 | Two codebases |

## Recommendation
PWA first (already in web), then Expo React Native app sharing `packages/` with web.
