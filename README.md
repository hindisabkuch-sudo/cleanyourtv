# cleanyourtv

Very light Apple TV style launcher for Android TV (tested target: Mi TV 4A, Android 9, 1 GB RAM).
Plain Android views, zero dependencies.

- Apps shown as banner tiles, focused tile scales up with a white outline
- Long press (hold OK) on a tile to pin / unpin; pinned apps come first
- Clock top right, Settings tile, auto refresh when apps are installed or removed

## Build
Push to GitHub. The "Build APK" workflow builds it. Download `launcher-apk` from the Actions run.

## Install
    adb install -r app-debug.apk
    adb shell cmd package set-home-activity com.cleanyourtv.launcher/.MainActivity

## Undo
    adb shell pm uninstall com.cleanyourtv.launcher

## Personalise
Top of `MainActivity.java`: `USER_NAME`, `CITY`, `LAT`, `LON` (weather from open-meteo.com, no API key).

## Cleaning PatchWall (only after this launcher works)
    adb shell pm disable-user --user 0 com.mitv.tvhome.atv
Undo:
    adb shell pm enable com.mitv.tvhome.atv
