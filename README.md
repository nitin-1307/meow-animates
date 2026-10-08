# Meow Animates

Meow Animates is a browser-based frame-by-frame 2D animation studio. It is a static site built with HTML, CSS, and JavaScript.

## Run locally

Serve this folder over HTTP rather than opening `index.html` as a `file://` URL. For example:

```powershell
python -m http.server 8000
```

Then open <http://localhost:8000>.

## Deploy with GitHub Pages

1. Create a GitHub repository named `meow-animates` and push the contents of this folder to its `main` branch.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**, choose `main` and `/(root)`, then save.
4. Wait for the Pages deployment to finish. The site URL will appear in the Pages settings.
5. In Firebase Console, open **Authentication → Settings → Authorized domains** and add the exact GitHub Pages hostname (for example, `your-name.github.io`).
6. Enable the sign-in providers used by the site under **Authentication → Sign-in method**. Email/Password must be enabled for email sign-in; configure Google and Microsoft credentials before using those providers.

The site loads `firebase-config.js` alongside `index.html`; keep both in the repository root. Firebase web-app configuration is client-side configuration, not a private credential. Never publish service-account JSON files, private keys, or Admin SDK credentials.

Projects are currently saved in the browser's local storage on the user's device; they are not synced to Firebase.
