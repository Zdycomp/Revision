# Revision

Android app (Kotlin + Jetpack Compose, Material 3) in package `com.example.revision`.
Gradle Kotlin DSL, version catalog at `gradle/libs.versions.toml`.

## Layout

- `app/src/main/java/com/example/revision/`
  - `MainActivity.kt` — entry point
  - `BakingScreen.kt` — Compose UI
  - `BakingViewModel.kt` — ViewModel holding screen state
  - `UiState.kt` — UI state types
  - `ui/theme/` — Color, Type, Theme
- `app/src/test/` — JVM unit tests (JUnit 4)
- `app/src/androidTest/` — instrumented tests (Espresso, Compose UI test)
- `htmlReport/` — generated coverage report. Do not edit by hand.
- `.idea/` — Android Studio project files

## Commands

Run from the repo root:

- Build debug APK: `./gradlew assembleDebug`
- Unit tests: `./gradlew testDebugUnitTest`
- Instrumented tests (needs a device or emulator): `./gradlew connectedDebugAndroidTest`
- Lint: `./gradlew lint`

## Conventions

- Follow the Kotlin official code style (`kotlin.code.style=official` in `gradle.properties`).
- Versions go in `gradle/libs.versions.toml`. Do not hardcode dependency versions in `app/build.gradle.kts`.
- Keep UI in Compose. Keep state in ViewModels and expose it through `UiState`.
- Do not commit `local.properties` or API keys. The Maps secrets plugin reads them from local files that are gitignored.

## Known issues

- `app/build.gradle.kts` is currently malformed. The `defaultConfig` block is not closed, and the `compileOptions` section contains garbled text, so Gradle will not configure the module. Fix this before running any build or test command.
