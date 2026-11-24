# MySpace PWA

A static, installable personal dashboard for notes, links, images and apps.

## Files
- `index.html` — complete HTML, CSS and JavaScript application
- `manifest.webmanifest` — PWA name, display settings and icons
- `service-worker.js` — app-shell caching for offline launch
- `icons/` — install icons, including iOS touch icon

## Deploy to GitHub Pages
1. Create a new GitHub repository, for example `myspace-pwa`.
2. Upload the contents of this folder to the repository root. `index.html` must be at the root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select branch `main` and folder `/(root)`, then Save.
6. Wait for GitHub Pages to publish. Open the HTTPS URL shown in the Pages settings.
7. Open the site once while online so the service worker can cache the app shell.

If the repository is named `myspace-pwa`, the URL usually looks like:
`https://YOUR-USERNAME.github.io/myspace-pwa/`

Do not remove the final repository path from the URL. The app uses relative paths and is configured for GitHub project pages.

## Install
- Android: open the HTTPS site in Chrome → menu → Install app / Add to Home screen.
- iPhone/iPad: open the site in Safari → Share → Add to Home Screen.
- Desktop: open the site in a supported browser and use its install icon/menu if offered.

## Data and backups
This starter version stores dashboard entries in the browser's localStorage on each device. It does **not** sync data between devices and is not a cloud database. Browser data can be cleared by device/browser settings, so export backups regularly.

For a backup, open the dashboard, open the browser developer console and run:
`mySpaceExport()`

To import a backup, choose a JSON file in the console and run:
`mySpaceImport(file)`

## Updating the app
After changing files, update `CACHE_NAME` in `service-worker.js` (for example `myspace-shell-v2`) and push the changes to GitHub. Then reload the website while online. If an older version remains, close and reopen the installed app or clear the site's cache.

## Notes
- PWA installation requires HTTPS, except during local development on `localhost`.
- iOS does not support the same `beforeinstallprompt` install button as Chromium browsers; use Safari's Share menu.
- Offline mode caches the app shell. External website links still need an internet connection.
- Images uploaded to this version are stored locally and limited to 1 MB each.
