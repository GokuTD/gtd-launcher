# Sideload guide

If GTD Launcher isn't yet on Play Store in your region, or you want to install it on a Fire TV / generic Android TV box that doesn't have Play Services, you can sideload the free APK.

## Prerequisites

- Android TV running Android 7.0+
- A way to put the APK on the TV (USB stick, file manager with cloud sync, network share, `adb`)

## Step 1 — Download the APK

Get the latest signed APK from the [Releases](https://github.com/GokuTD/gtd-launcher/releases) page:

- `GTDLauncher-1.0-release.apk` (~7.5 MB)
- `GTDSetup-1.0-release.apk` (~1.9 MB) — phone companion (optional)

For the plugin: get `GTDPlugin-1.0-release.apk` from the [plugin releases](https://github.com/GokuTD/gtd-plugin/releases).

## Step 2 — Allow unknown sources

On your TV: **Settings → Security & restrictions → Unknown sources → enable** (the exact path varies by manufacturer).

## Step 3 — Install

Pick the method that fits your setup:

### Option A: file manager

Install [Solid Explorer](https://play.google.com/store/apps/details?id=pl.solidexplorer2) or [X-plore](https://play.google.com/store/apps/details?id=com.lonelycatgames.Xplore) on the TV. Drop the APK on a USB stick / cloud / SMB share, browse to it from the file manager, tap install.

### Option B: ADB

If you have ADB set up:

```
adb install GTDLauncher-1.0-release.apk
adb install GTDPlugin-1.0-release.apk    # optional
```

### Option C: Send Files to TV (mobile app)

[Send Files to TV](https://play.google.com/store/apps/details?id=com.yablio.sendfilestotv) on phone + same on TV → push the APK over the local network → tap install on the TV.

## Step 4 — Set as Home

After install: **Settings → Apps → Default apps → Home app → GTD Launcher**.

Press the HOME button on your remote — should open GTD Launcher.

## Step 5 — Grant permissions

The launcher's first-run wizard will guide you through enabling:
- Notification access (recommendations row + Now Playing badge)
- WRITE_SECURE_SETTINGS (auto-enabled via the QR pairing flow with [GTD Setup](Pairing-Guide), or manually via ADB)
- Accessibility service (optional — for global remote remap, idle detection)
- Default voice assistant (optional — to suppress the white assistant ball)

## Step 6 — (Optional) install GTD Setup

To skip typing your Emby URL / passwords / API keys with the TV remote, install **GTD Setup** on your phone and pair via QR. See the [Pairing guide](Pairing-Guide).

## Updating

When a new release ships, just install the new APK over the old one (same signature). All your settings and Premium status are preserved.

## Buying Premium for a sideloaded install

You don't need a special "premium APK". The same sideloaded APK reconciles with Play Billing:

1. Open the launcher → Settings → Premium → Unlock for €7
2. Pay via your Google account
3. Premium activates automatically

Works as long as the device has Google Play Services installed (so most Android TV devices except Fire TV).
