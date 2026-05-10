# Troubleshooting

## The launcher

### Apps don't appear / channels are empty

Probably the `READ_TV_LISTINGS` permission was denied. Re-run the [pairing flow](Pairing-Guide) or grant manually:

```
adb shell pm grant com.gtd.tv.launcher android.permission.READ_TV_LISTINGS
```

Then force-stop the launcher (or reboot the TV).

### Recommendations row is empty

Notification access not granted. Settings → Apps → Special access → Notification access → enable GTD Launcher. (The pairing flow grants this automatically.)

### Default voice assistant overlay (white circle) appears every time I press the search button

The launcher ships its own Voice Interaction Service that suppresses it, but the system needs a reboot to pick it up after first install. Reboot the TV once. If it persists: Android Settings → System → Languages & input → Default voice assistant → GTD Launcher.

### Custom wallpaper file picker shows nothing

`READ_EXTERNAL_STORAGE` not granted. The pairing flow (since v1.0) grants it automatically. Manual:

```
adb shell pm grant com.gtd.tv.launcher android.permission.READ_EXTERNAL_STORAGE
```

### Wallpaper looks "half" / cropped at the top

That's the **shadow overlay** — a vertical gradient that darkens the top of the wallpaper so card text is readable. Settings → Appearance → Wallpaper → Shadow overlay → reduce opacity to 0 to disable.

### Boot direct doesn't work / Android TV launcher takes over

Settings → Apps → Default apps → Home app → GTD Launcher.

## The plugin (Emby integration)

### Plugin can't connect to Emby

Three options to debug:

1. **Server URL is reachable from the TV?** Try `adb shell curl -v <your-emby-url>`. If that fails, network issue (firewall, AP isolation, wrong IP).
2. **Emby Connect**: try the "Sign in with Emby Connect" button instead of manual URL — uses Emby's cloud relay, doesn't need direct LAN access.
3. **Self-signed HTTPS**: the plugin trusts self-signed certs by default for Emby. If it's still failing, check the Emby URL (some servers redirect HTTP→HTTPS and our client doesn't follow).

### Football team search returns nothing

You haven't entered an api-football.com key. Get a free one at [dashboard.api-football.com](https://dashboard.api-football.com) → Plugin → Football → API Keys → paste under "API-Football key" → Save.

### Oppo control: keys do nothing

1. Verify Oppo TCP is reachable: `adb shell nc -zv 192.168.0.111 23` (replace IP with your Oppo's). Should say "succeeded".
2. Plugin → Oppo → check status indicator (LED on left nav).
3. Toggle Power: needs the Oppo to be in screensaver / playing / paused state — if the player is in deep sleep, sometimes you have to hit it twice.

### Samsung soundbar HDMI switch fails

Samsung's local IP control needs:
- Soundbar on same LAN as Shield (no AP isolation)
- "IP Control" enabled in SmartThings app
- Correct IP — they sometimes change after router reboot, double-check via `ping`

### Foco salta cuando vuelvo de una app

Should be fixed in v1.0+ (we cancel the deferred reset in onPause). If you still see it, capture a logcat right after returning from the app and open an issue:

```
adb logcat -d -t 500 | grep -E "MainActivity|FocusDebug|restoreFocus"
```

## Setup app (phone)

### "Waiting for TV approval" never completes

Look at the TV — there's a "Allow Network debugging?" dialog waiting for your input. Tick "Always allow from this computer" and accept.

### QR scanner refuses to open

The first time, Android may prompt for camera. Allow it.

### Phone says paired but launcher acts unchanged

Force-stop the launcher (Android settings → Apps → GTD Launcher → Force stop) and reopen — pairing changes are picked up on cold start.

## Still stuck?

[Open an issue](https://github.com/GokuTD/gtd-launcher/issues/new/choose) with:
- TV model + Android TV version (Settings → System → About)
- Launcher version (`adb shell dumpsys package com.gtd.tv.launcher | grep versionName`)
- What you tried, what happened, what you expected
- Logcat if relevant: `adb logcat -d -t 500 > logcat.txt`
