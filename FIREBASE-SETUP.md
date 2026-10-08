# Firebase Authentication setup

Meow Animates uses Firebase Authentication for email/password, Google, and Microsoft sign-in. User credentials are stored and managed by Firebase Authentication. Animation projects remain saved in the user's browser on that device; this setup does not sync animation files to Firebase.

## Connect a Firebase project

1. In the [Firebase console](https://console.firebase.google.com/), create or open a project.
2. Register a **Web app** from the project overview and copy its Firebase configuration object.
3. Paste the config values into `firebase-config.js`, replacing the empty strings. The `apiKey`, `authDomain`, `projectId`, and `appId` values are required.
4. Open **Authentication → Sign-in method** and enable **Email/Password**, **Google**, and **Microsoft** as needed.
5. Under **Authentication → Settings → Authorized domains**, add the domain serving Meow Animates, including the GitHub Pages hostname if deployed there. Use an HTTP(S) development server for local testing; OAuth sign-in does not work from a `file://` URL.
6. Deploy `index.html`, `firebase-config.js`, and the logo asset together on the same site.

Firebase web app config values are public client identifiers, not service credentials. Do not put a service-account JSON file, private key, or Admin SDK credentials in this site or repository. Protect any Firebase database or storage by enabling authentication and writing restrictive Security Rules before adding client access.

For Google OAuth, Firebase can use its managed provider setup. Microsoft sign-in requires an Azure application and its provider credentials. Configure provider credentials in Firebase Console before enabling each button for users.
