# Tip Time

Tip Time is a simple Android tip calculator app built with Kotlin and Jetpack Compose.

## Overview

This project demonstrates a Compose-based Android app that calculates a tip amount from a bill amount and a tip percentage.

## Features

- Enter bill amount
- Enter tip percentage
- Display formatted tip amount
- Compose UI with Material 3 styling
- Edge-to-edge layout support

## Project Structure

- `build.gradle.kts` - root Gradle configuration
- `settings.gradle.kts` - project settings and module inclusion
- `app/build.gradle.kts` - Android app module configuration
- `app/src/main/java/com/example/tiptime/MainActivity.kt` - app entry point and UI logic
- `app/src/main/java/com/example/tiptime/ui/theme/` - theme definitions and colors
- `app/src/main/res/values/strings.xml` - string resources
- `app/src/main/res/values/themes.xml` - theme styles
- `app/src/main/res/values/colors.xml` - color palette
- `app/src/main/AndroidManifest.xml` - app manifest and launch activity

## Technical Details

- Kotlin
- Jetpack Compose
- AndroidX Material3
- Minimum SDK: 26
- Target SDK: 36
- Java compatibility: 11

## Build and Run

From the project root:

```bash
./gradlew clean assembleDebug
```

Open the project in Android Studio and run the `app` module on an emulator or device.

## Usage

1. Enter the bill amount.
2. Enter the tip percentage.
3. The calculated tip amount is displayed automatically.

## Notes

- The tip amount uses the system currency formatting.
- The current implementation defaults an invalid tip input to `15.0` percent.

## Potential Improvements

- Add rounding options
- Show total amount including tip
- Add bill splitting support
- Add validation and error handling for empty or invalid input
