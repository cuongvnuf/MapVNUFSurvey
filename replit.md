# Ground for Android

## Project Overview

Ground is an open-source, map-first data collection and analysis platform built by Google. It connects offline data collection with cloud-based storage and computation (Firebase). Targeted at community organizers, conservationists, and humanitarian workers.

**GitHub:** https://github.com/google/ground-android

## Architecture

This is a **native Android application** — it cannot run as a web server or be previewed in a browser.

### Modules
- **`:app`** — Main Android application (Kotlin, Jetpack Compose, Hilt DI)
- **`:core:domain`** — Kotlin Multiplatform business logic & models
- **`:core:ui`** — Kotlin Multiplatform shared UI (Compose Multiplatform)
- **`:e2eTest`** — End-to-end tests
- **`:sharedTest`** — Shared test utilities

### Key Technologies
- **Language:** Kotlin (primary), Java (legacy)
- **UI:** Jetpack Compose + Compose Multiplatform
- **DI:** Hilt (Dagger)
- **Local DB:** Room
- **Backend:** Firebase (Firestore, Auth, Storage, Remote Config)
- **Maps:** Google Maps SDK
- **Async:** Kotlin Coroutines + Flow
- **Build:** Gradle 9.4.1 with Version Catalogs

## Build System

- **Build tool:** Gradle Wrapper (`./gradlew`)
- **Java:** GraalVM 22.3.1 (JDK 19)
- **Android SDK:** Requires Android SDK with compileSdk 36, minSdk 24

## Workflow

The "Start application" workflow runs `./gradlew assembleDebug` to build a debug APK. Full Android SDK is needed for complete compilation — the Android SDK platform tools are not available in this Replit environment, so the build will configure but may fail at compilation.

## Development Notes

- Firebase configuration (`google-services.json`) is required for full functionality
- Google Maps API key is required for map features
- See `local.defaults.properties` for local configuration options
- See `CONTRIBUTING.md` for contribution guidelines

## Environment Variables / Secrets

None currently configured. Firebase and Maps keys are typically embedded via `google-services.json` and `local.properties`.
