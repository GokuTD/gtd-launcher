# FAQ

## General

### What is GTD Launcher?

A custom launcher for Android TV that replaces the stock home screen. Built on the proven Leanback foundation but fully rewritten for speed, customisation and zero ads.

### Is it free?

The free tier ships everything you need to use the launcher daily — channels, themes, layouts, search, hidden apps, favourites, watch next, basic remote remap, etc. **Premium (€7 one-time)** adds 8 extra themes, RGB/Neon glow, wallpaper engine adjustments, per-app icons, multi-button remap and Google Drive backup. See the [README comparison](https://github.com/GokuTD/gtd-launcher#free-vs-premium-at-a-glance).

### Subscription? Recurring fee?

**No.** Premium is a single €7 purchase via Google Play Billing. Reinstall on any device signed in with the same Google account and Premium restores automatically.

### What devices are supported?

- ✅ Android TV 7.0+ (API 24+)
- ✅ Best on Nvidia Shield, Chromecast with Google TV, Mecool / Onn / Walmart streamers
- ✅ Most generic Android TV boxes
- ⚠️ Fire TV — works as a sideloaded app but Amazon's launcher blocks setting it as Home (no fix on our side)
- ❌ Not for phones / tablets — designed for TV remote navigation only

### Does it collect any data?

**No.** No telemetry, no analytics, no crash reporter, no advertising SDK, no user account. Everything you configure stays on your device. Optional integrations (Google Drive backup, Emby plugin, TMDB / football APIs) only activate when you explicitly enable them. See the [Privacy Policy](https://gokutd.github.io/gtd-policy/).

## Plugin & integrations

### Do I need GTD Plugin?

No, the launcher works standalone. The plugin adds Emby integration: dynamic wallpapers, ambient screensaver, native Android TV channels populated from your library, football overlays, and an Oppo UDP-203/205 remote. Install it if you have an Emby server.

### Do I need an Emby server?

Only if you install the plugin and want its features. The launcher itself doesn't require one.

### Can I use Jellyfin / Plex instead?

The plugin is Emby-specific. Jellyfin support is on the roadmap but not yet shipped. Plex has its own native Android TV launcher integration so the GTD plugin focuses on Emby.

## Premium

### Does Premium work on every device I sign in with?

Yes. Play Billing reconciles purchases across devices using your Google account.

### What if I sideload the APK from GitHub Releases?

Same APK. It runs in **free mode** until you purchase Premium via Google Play. After purchase, Play Billing recognises the purchase even on sideloaded APKs (same package + signature) and unlocks the full feature set.

### Refund policy?

Standard Google Play 48-hour refund window.

## Customisation

### Can I have rotating wallpapers (slideshow)?

Yes (Premium). Settings → Appearance → Wallpaper → enable Slideshow, then drop multiple images in the same folder. The launcher cycles through every supported image (`jpg`, `jpeg`, `png`, `webp`, `bmp`) in that folder at the configured interval.

### Custom video / GIF wallpaper?

Yes (Premium). Pick an `.mp4` / `.webm` (video) or `.gif` (animated) the same way as a static image.

### Icon packs?

Yes (Premium). Install any Android icon pack from Play Store, then Settings → Appearance → Cards → Apply icon pack.

### Per-app custom icons?

Yes (Premium). Long-press any app → Change icon → pick an image from storage.

## Remote / Buttons

### Can I remap remote buttons?

Yes. The free tier allows **one** custom button mapping; Premium unlocks unlimited. Settings → Remote Control → Add mapping.

### Why is the search button hijacking my voice assistant?

Probably the system Assistant overlay. The launcher ships its own Voice Interaction Service (VOIS) that suppresses the white voice ball. If it's not active, set it manually in Android Settings → System → Languages & input → Spoken language → Default voice assistant → GTD Launcher.

## Troubleshooting

See the dedicated [Troubleshooting](Troubleshooting) page.
