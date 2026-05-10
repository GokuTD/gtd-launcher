# Pairing the launcher with GTD Setup

GTD Setup is a tiny mobile app that handles the part of the launcher's first-run flow that's painful to type with a TV remote: Emby login, your Oppo / soundbar IPs, TMDB / football API keys, and granting `WRITE_SECURE_SETTINGS` over ADB.

Instead of typing all that on the TV, you scan a QR with your phone.

## What you'll need

- The launcher installed and running on your TV
- An Android phone (Android 7+) on the **same Wi-Fi network** as the TV
- The Setup APK on your phone — get it from [GTD Launcher releases](https://github.com/GokuTD/gtd-launcher/releases) (`GTDSetup-1.0-release.apk`)

## Step 1 — Install GTD Setup

Drop the APK onto your phone (USB cable, email yourself the link, Send Files to TV…) and install. Allow unknown sources if prompted.

## Step 2 — Open the QR on the TV

In the launcher: **Settings → Easy setup from phone**. A QR appears on the right side, with the TV's IP and ADB port.

> **First-time devices only**: when the phone first connects, the TV pops a "Allow Network debugging?" dialog with the phone's RSA fingerprint. **Tick "Always allow from this computer"** then "Allow". This is the system's standard ADB pairing flow.

## Step 3 — Scan from the phone

Open **GTD Setup** on the phone → **Setup permissions** → camera opens → point at the TV → instant scan.

The phone connects to the TV over ADB and grants:
- `WRITE_SECURE_SETTINGS` — lets the launcher flip notification listener / assistant / accessibility on
- `READ_TV_LISTINGS` — channel enumeration for the home rows
- `RECORD_AUDIO` — voice search
- `ACCESS_FINE_LOCATION` — weather widget
- `READ_EXTERNAL_STORAGE` — custom-wallpaper file picker

## Step 4 — Configure (optional, anytime)

Back in GTD Setup, tap **Configure API keys** or **Configure Login & IPs** to push:

- Emby server URL + username + password
- Oppo player IP (and MAC for Wake-on-LAN)
- NAS IP
- Samsung soundbar IP
- TMDB API key
- football-data.org API key
- api-football.com API key

Tap **Send to TV**. Empty fields are skipped — only filled ones get sent.

## Troubleshooting

### "Waiting for TV approval" hangs

You missed the "Allow Network debugging?" dialog on the TV. Just look at the TV screen and accept it. If the dialog never appears, restart the launcher's setup wizard.

### Phone can't reach TV

Both must be on the same network. AP isolation (a router setting) blocks intra-WiFi traffic. Disable it: router admin → WiFi → Advanced → AP isolation = OFF.

### Wrong IP

The QR encodes the TV's current IP. If your TV's DHCP lease changes between scans (uncommon but possible), generate a fresh QR by reopening the setup wizard.
