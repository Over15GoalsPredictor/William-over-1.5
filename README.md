# Over 1.5 Goals Predictor — Android starter

## What is included
- Native Android Studio project (Kotlin).
- Today's fixtures requested in `Africa/Johannesburg` time.
- Schedules a daily background fixture refresh using Android WorkManager (Android may defer it for battery optimization).\n- Manual scan retrieves provider Over 1.5 signals.
- Displays only provider predictions that explicitly indicate Over 1.5.
- No match-winner or other betting markets.

## Important probability limitation
API-Football's documented prediction response includes an Under/Over recommendation, but does not document a calibrated numeric probability for Over 1.5. This starter therefore **does not fabricate a 90% probability** and does not label candidates as 90%+ picks. To enforce a genuine 90% threshold, add a validated statistical model trained and back-tested on historical match outcomes (or connect a data provider that supplies calibrated Over 1.5 probabilities).

## Setup
1. Install Android Studio.
2. Open this folder as a project.
3. Let Gradle sync.
4. Run on an Android device/emulator (Android 8.0+).
5. Obtain an API key from https://dashboard.api-football.com/
6. Enter the key in the app and tap Save API key, then Scan Today's Fixtures.

## API notes
- Fixtures: `GET https://v3.football.api-sports.io/fixtures?date=YYYY-MM-DD&timezone=Africa/Johannesburg`
- Predictions: `GET https://v3.football.api-sports.io/predictions?fixture=FIXTURE_ID`
- Header: `x-apisports-key: YOUR_KEY`
- API usage is subject to the provider's subscription limits.
- This starter stores the key locally on the device. For a public production app, put API calls behind a secure backend; never ship a shared private API key in a distributed APK.

## Not yet production-ready
This is a starter project, not a signed APK. It currently scans when the user taps the button; scheduled background refresh, secure backend key storage, persistent history, notifications, and a validated probability model must be added before production release.
