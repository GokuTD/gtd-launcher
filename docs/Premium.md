# Premium & Billing

## What Premium unlocks

The €7 one-time purchase activates these features:

| Area | Free | Premium |
|---|---|---|
| **Themes** | 4 (Default, AMOLED, Arctic, Ocean) | 12 (+ Neon Night, Sunset, Forest, Ruby, Amethyst, Rose, Teal, Amber) |
| **Card glow** | Dynamic, Color | + RGB, Neon |
| **Wallpaper** | Static images, plugin source | + Brightness, contrast, saturation, hue, blur, colour filter, slideshow |
| **Per-app icons** | — | Override any app icon with your own image |
| **Icon packs** | — | Apply any third-party icon pack from Play Store |
| **Multi-button remap** | 1 mapping | Unlimited |
| **Cloud backup** | Local export/import to JSON | + Google Drive sync, auto-restore on reinstall |
| **Status bar widgets** | Clock, Wi-Fi indicator | + extra widgets (weather, etc.) |

The plugin and setup app are sold separately. The plugin has its own €7 Premium (unlocks ~30 themes + custom theme editor + full Oppo remote mapping). The setup app is permanently free with no IAP.

## How billing works

- **Purchased via**: Google Play Billing (in-app purchase, ID `gtd_launcher_premium` for the launcher, `gtd_plugin_premium` for the plugin)
- **Type**: Managed product (one-time purchase, no subscription)
- **Reconciliation**: the app queries Play Billing on every launch. If Play says "owned" → Premium activates. If Play says "not owned" → Premium deactivates. This means:
  - Reinstall on a new device → Premium restores automatically (same Google account)
  - Refund via Play Store → Premium deactivates on next launch
  - Sideloaded APK + Play purchase → Premium still activates (signature matches)

## Refunds

Standard Google Play 48-hour automatic refund. Beyond 48 hours, request via Play Store ("My orders" → request refund). Once Google Play processes, the app picks up the change on next launch.

## I bought Premium but it's not active

1. Open the launcher → Settings → Premium → wait a few seconds for the status row to update
2. Tap "Unlock for €7" once more — Play Billing might just need a query
3. If that fails: force-stop the launcher (Android settings → Apps → GTD Launcher → Force stop), reopen
4. Verify in the Play Store app: My subscriptions / orders → "GTD Premium" should be listed with status Owned
5. If still missing, [open an issue](https://github.com/GokuTD/gtd-launcher/issues/new/choose) with the order ID

## Family sharing

Google Play family library doesn't extend to in-app purchases. If your spouse / kid wants Premium too, they'd need to buy on their own account. (Same constraint as every other paid app on Play.)

## Bulk / commercial licensing

Need 50+ copies for a business? Email `gokukinto@gmail.com` for a quote.
