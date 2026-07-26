# Flight Light — firmware releases

Public release channel for **Flight Light** ("The Earl of Airside"). Contains
built firmware images and the update manifest only.

The light checks `manifest.json` when you tap **Check for updates** on its
About page, and installs `url` if `version` is newer than what it is running.
It fetches this unauthenticated, which is why this repo is public — the
development source lives in the private `flight-light` repo.

| File | Purpose |
|---|---|
| `manifest.json` | Latest release the light should offer |
| `firmware/flightlight-<version>.bin` | The image itself |

**Publishing a release:** drop the new `.bin` into `firmware/`, update
`version`, `url`, `size` and `sha256` in `manifest.json`, and push to `main`.
Only the current and previous images are kept, to stop the repo bloating.

Installing a build never removes the one it replaces — the previous version
stays in the light's other flash slot, so **Go back a version** on the About
page restores it in seconds without downloading anything.
