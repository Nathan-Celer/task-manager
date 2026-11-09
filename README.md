# Organizer: setup (about 10 minutes, all free)

Everything runs on your own Firebase project: the data (Firestore), the sign-in, and the hosting of the page. No GitHub needed.

## 1. Create the Firebase project (browser)
1. https://console.firebase.google.com > Add project (skip Analytics).
2. Build > Firestore Database > Create database > production mode, any region.
3. Build > Authentication > Get started > Sign-in method > Google > Enable.
4. Project settings (gear) > Your apps > Web (</>) > register the app (tick nothing else). Copy the config values into `firebase-config.js`.

## 2. Deploy (one-time, in a terminal on your computer, needs Node.js)
```
npm install -g firebase-tools
firebase login
cd <this folder>
firebase use --add        # pick your project
firebase deploy
```
This publishes the page and the security rules (`firestore.rules`). It prints your URL: `https://<project>.web.app`. That domain is already authorized for sign-in.

## 3. Install
- Phone: open the URL, sign in with Google, then "Add to Home Screen" (iOS Safari: Share > Add to Home Screen; Android Chrome: menu > Install app).
- Desktop: open the URL in Chrome or Edge, click the install icon in the address bar.

Use the same Google account on both devices. Offline changes are kept on the device and sent when it reconnects.

## Updating later
Edit the files and run `firebase deploy` again.

## Alternative: GitHub Pages
Upload the files to a repo and enable Pages, then add `<username>.github.io` under Authentication > Settings > Authorized domains, and paste `firestore.rules` into Firestore > Rules.
