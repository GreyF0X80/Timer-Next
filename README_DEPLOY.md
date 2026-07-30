# Timer 2.0.0

Timer is an installable, offline-first interval timer for HIIT, Tabata, strength and cardio sessions. It supports configurable preparation, work, recovery, rounds and periodic extra phases without requiring an account or backend.

## Package structure

- `index.html` — complete application interface and timer engine.
- `manifest.webmanifest` — PWA identity, icons and installation metadata.
- `service-worker.js` — offline cache and update lifecycle.
- `Logo-Blu.svg` — KrioPlanet theme logo.
- `icons/` — favicon, Apple touch icon, standard and maskable PWA icons.
- `PRIVACY_POLICY.md` — privacy information for the web release.
- `SUPPORT.md` — support and troubleshooting information.

## Publishing

1. Upload every package file without changing the directory structure.
2. Serve the application over HTTPS. `localhost` may be used for development.
3. Open the published URL once while online and verify that the Service Worker reaches the activated state.
4. Reload the page and install Timer from the browser installation command or, on iPhone/iPad, with **Share → Add to Home Screen**.
5. Close the installed app completely, disable the network and reopen it to validate offline startup.

Static hosting such as GitHub Pages, Cloudflare Pages or Netlify is sufficient. No backend or database server is required.

## Offline operation and cache updates

The Service Worker precaches every required application asset. Installation fails instead of silently completing when an essential asset is missing. During activation, obsolete Timer caches are removed while caches belonging to unrelated applications on the same origin are preserved.

For every published application update:

1. change `CACHE_NAME` in `service-worker.js`;
2. publish all changed assets together;
3. open the app online and reload once;
4. verify the new Service Worker and offline relaunch before removing the previous deployment.

The final cache for this release is `timer-v2.0.0-2026-07-30`.

## Installation

Timer can be installed as a PWA on compatible mobile and desktop browsers. The manifest does not lock orientation: portrait and landscape are both supported. Browser installation wording varies by platform.

## Themes and local branding

Timer includes:

- Standard;
- KrioPlanet;
- Custom.

The Custom theme stores the selected name and colors in `localStorage`. A personal PNG, JPEG, WebP or SVG logo up to 2 MB is stored locally in IndexedDB. Functional phase colors remain fixed for clarity.

## Languages

The default mode is **Automatic — Device language**. Italian and English are supported. Unsupported device languages fall back to English. A manual selection overrides automatic detection and persists offline.

## Local privacy

Timer does not require an account and the current PWA does not send workout, preference or branding data to a server. Workouts and preferences remain in browser storage on the device. See `PRIVACY_POLICY.md` for the complete web-release statement.

## Browser and device limitations

- Service Workers require HTTPS or localhost.
- Audio must be unlocked by a user interaction and can be affected by browser, silent-mode and Bluetooth behavior.
- Vibration is not available in every browser, including some Apple platforms.
- Screen Wake Lock is used only when supported and permitted by the browser. On unsupported devices the timer continues to operate, but the screen may dim or lock.
- Storage can be cleared by the user, the operating system or browser data-management tools.
- Installing over an older Home Screen copy may require removing and reinstalling the icon when platform metadata is strongly cached.

## Test procedure

Before promotion, complete a release test matrix covering:

- clean online installation and offline relaunch;
- update from the previous cache;
- timer transitions, pause, skip, background recovery and completion;
- portrait and landscape layouts;
- Standard, KrioPlanet and Custom themes;
- Italian, English and unsupported-language fallback;
- sound, vibration and Wake Lock behavior on physical devices.

Automated validation cannot replace physical tests for audio routing, vibration, safe areas, Home Screen installation, operating-system background behavior or Wake Lock.

## Rollback

1. Restore the previously validated package on the host.
2. Give its Service Worker a new cache name so browsers treat the rollback as an update.
3. Publish the restored files together.
4. Open and reload online, then verify offline startup.
5. Do not reuse the failed release cache name.

## Release

- Product: Timer
- Version: 2.0.0
- Distribution: offline-first PWA and standalone HTML
- Copyright: © 2026 MC
