# Smart Clock Live — Native Android Studio Project (Kotlin + Jetpack Compose)

A complete, buildable Android 10+ (API 29–35) application built with Kotlin, Jetpack Compose, Material 3, DataStore Preferences, WorkManager, OkHttp, Foreground Services, and Jetpack Glance Home Screen Widgets.

## Features Implemented
- **Real-Time Digital Clock**: Synchronized 1000ms ticker (`HH:MM:SS`), AM/PM indicator, 12/24-hour toggle, automatic system timezone detection, and localized English & Bengali (`বাংলা`) numerals/dates.
- **Live Currency Exchange**: Fetches live rates for **USD, EUR, GBP, AED, SAR, BDT, JPY, CNY, EGP** with offline DataStore caching and automatic network fallback.
- **Always On Display (AOD)**: Dedicated AMOLED `#000000` `AlwaysOnDisplayActivity` with burn-in pixel shifting, automatic brightness dimming after 12s inactivity, and double-tap exit.
- **Lock Screen Notification**: `ClockForegroundService` (`specialUse` foreground service type for Android 14+) showing real-time clock, date, and top selected currency rates on the lock screen. Automatically slows ticks to 60s when the screen turns off to preserve battery.
- **Home Screen Widgets**: Three Jetpack Glance widgets (`2×1` Compact, `4×2` FX, `4×3` Studio) using hardware-accelerated `TextClock` for battery-free real-time `HH:MM:SS` ticking plus live currency rates and a tap-to-refresh action.
- **Customization & Settings**: Multiple clock styles, font families, custom clock colors, background surfaces, adjustable clock scale, AMOLED/Dark/Light modes, portrait & landscape layouts, battery optimization shortcut, and instant English/Bengali switching.

## How to Build the Installable APK in Android Studio
1. Open the `android-app` folder in **Android Studio Ladybug (2024.2)** or newer.
2. Wait for Gradle Sync to download dependencies (`AGP 8.7.3`, `Kotlin 2.0.21`, `Gradle 8.9`).
3. To build an installable APK from Android Studio:
   - Menu: **Build → Build Bundle(s) / APK(s) → Build APK(s)**
4. Or from terminal inside `android-app/`:
   ```bash
   ./gradlew assembleDebug
   # Output: app/build/outputs/apk/debug/app-debug.apk

   ./gradlew assembleRelease
   # Output: app/build/outputs/apk/release/app-release.apk
   ```
