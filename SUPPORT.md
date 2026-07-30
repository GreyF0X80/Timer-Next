# Timer 2.0.0 — Support

## Supported release

This document applies to Timer 2.0.0, distributed as an offline-first PWA and standalone HTML application.

## Installation requirements

- Use a current browser with JavaScript enabled.
- Publish or open the hosted PWA over HTTPS; localhost is supported for development.
- Open the app online once before testing offline mode.
- On iPhone and iPad, use Safari and **Share → Add to Home Screen** when a Home Screen installation is required.

## Common troubleshooting

### The app does not install

Confirm that the manifest, Service Worker, icons and all listed assets return successfully over HTTPS. Clear the site's data, reload online and retry installation.

### An old version still appears

Close every Timer tab and installed window, reopen the hosted page online and reload. If platform metadata or icons remain stale, remove the Home Screen installation and install it again.

### Offline startup fails

Reconnect, open the app and wait for the Service Worker to activate. Reload once, close the app, disable the network and retry. A missing core asset intentionally prevents completion of the offline installation.

### Audio is silent

Tap Start or a sound-preview button to unlock Web Audio. Check app volume, system volume, silent-mode behavior and Bluetooth routing. Platform restrictions can override app preferences.

### Vibration is unavailable

The Vibration API is not supported by every browser and device. The timer remains functional without vibration.

### The screen dims or locks

Screen Wake Lock is requested only during an active, visible workout and only when supported. Browser permissions, power-saving modes or operating-system restrictions may prevent it.

### A custom logo disappears

The logo is stored in IndexedDB for the current site and browser profile. Clearing site data, using private browsing or changing origin removes or separates that storage.

## Data reset

Use **Reset Settings** to restore application preferences without deleting saved workouts. Delete workouts individually from the library. Use browser site-data controls to remove all stored data and offline files.

## Reporting an issue

Provide the following information to the publisher or deployment administrator:

- Timer version;
- device and operating-system version;
- browser and whether the app is installed;
- portrait or landscape orientation;
- exact steps to reproduce;
- expected and observed behavior;
- whether the issue persists after an online reload.

Do not include sensitive personal or health information.
