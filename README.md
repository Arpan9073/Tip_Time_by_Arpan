# Tip Time

Tip Time is a small Android tip calculator app built with Kotlin and Jetpack Compose.

## Overview

This project is a Compose-first sample app that computes a tip amount from a bill value and a tip percentage. It also offers an optional rounding toggle and uses Material 3 styling with dynamic theming support on Android 12+.

## App Behavior

- Enter a bill amount.
- Enter a tip percentage.
- Toggle `Round Up Tip?` to round the tip to the next whole currency unit.
- The app displays the calculated tip formatted in the device currency.
- Invalid bill input is treated as `0.0` and invalid tip input falls back to `15.0` percent.

## Features

- Kotlin + Jetpack Compose UI
- Material 3 design
- Edge-to-edge layout with `enableEdgeToEdge()` support
- Vertical scrolling support for smaller screens
- Currency-formatted tip output
- Round-up tip option
- Dynamic color support for Android 12+ via Compose theme

## Project Structure

- `build.gradle.kts` - root Gradle configuration
- `settings.gradle.kts` - project settings and module inclusion
- `gradle/libs.versions.toml` - dependency and plugin version catalog
- `app/build.gradle.kts` - Android app module configuration
- `app/src/main/java/com/example/tiptime/MainActivity.kt` - app entry point, UI composables, and business logic
- `app/src/main/java/com/example/tiptime/ui/theme/Theme.kt` - Material 3 theme definitions
- `app/src/main/res/values/strings.xml` - app text resources
- `app/src/main/AndroidManifest.xml` - application manifest and launch activity

## Technical Details

- Kotlin
- Jetpack Compose
- AndroidX Material 3
- Minimum SDK: 26
- Target SDK: 36
- Java compatibility: 11

## Build and Run

From the project root on Windows:

```powershell
.
\gradlew.bat clean assembleDebug
```

Or in a Unix-like shell:

```bash
./gradlew clean assembleDebug
```

Then open the project in Android Studio and run the `app` module on a device or emulator.

## Live Preview

The project also includes a Compose preview function in `MainActivity.kt` for inspecting the UI in Android Studio.

## Notes

- The tip calculation is implemented in `calculateTip(amount, tipPer, roundUp)`.
- Tip text is displayed using `R.string.tip_amount` and `NumberFormat.getCurrencyInstance()`.
- The app uses `TextField` composables for input and a `Switch` for the round-up option.

## Possible Improvements

- Show total bill amount including tip
- Add bill splitting support
- Improve validation and error messaging for empty or invalid input
- Add accessibility labels and focus handling
- Add unit tests for tip calculation logic

## Implementation details (updated 2026-06-27)

- Entry point UI: `Tip_Time` composable is launched from `MainActivity` inside a `Scaffold`.
- Tip calculation: `calculateTip(amount, tipPer, roundUp)` computes the tip and returns a currency-formatted `String` via `NumberFormat.getCurrencyInstance()`; when `roundUp` is true it uses `kotlin.math.ceil`.
- Inputs: amount and tip percentage are captured with `EditNumberField` text fields (defaults: amount = `0.0`, tip% = `15.0`). Leading icons use `R.drawable.money` and `R.drawable.percentage`.
- UI details: the activity calls `enableEdgeToEdge()` and the layout applies `statusBarsPadding()` and `verticalScroll(rememberScrollState())` for small screens. The calculated tip is shown using `MaterialTheme.typography.displaySmall`.
- Round-up control: provided by `RoundUpTip` composable which uses a `Switch`.
- Preview: `TipTimePreview` uses `showSystemUi = true` so the Compose preview shows system chrome.

If you'd like, I can expand the README with a small code snippet showing `calculateTip()` usage or add a short changelog entry describing why these UI changes were made.
