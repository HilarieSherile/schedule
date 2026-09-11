# Daily Planner

A single self-contained HTML file (no build step) that stores its data in
Firebase Firestore, so it syncs across any device where you open this same
page with the same Firebase config filled in.

## Setup

1. **Create a Firebase project** (or reuse one you already have) at
   https://console.firebase.google.com.
2. In the project, enable **Firestore Database** (Build > Firestore Database
   > Create database — test mode is fine to start).
3. Go to **Project settings > Your apps**, add a **Web app**, and copy the
   `firebaseConfig` object it gives you.
4. Open `daily-planner.html` and paste your values into the
   `firebaseConfig` object near the top of the `<script>` block (search for
   `YOUR_API_KEY`).
5. Push this repo to GitHub and enable **GitHub Pages** (Settings > Pages >
   Deploy from branch > main > root).
6. Open the resulting `https://<you>.github.io/<repo>/daily-planner.html`
   URL on any device — they'll all read/write the same Firestore project, so
   changes sync.

## Notes / next steps

- Firestore's free tier is generous for personal use; you won't hit limits
  from normal daily-planner usage.
- The config in step 4 is visible to anyone who views the page source. For a
  personal single-user tool this is usually fine, but if you want it locked
  down, add [Firestore security rules](https://firebase.google.com/docs/firestore/security/get-started)
  restricting reads/writes (e.g. requiring Firebase Auth sign-in).
- Right now anyone with the URL can read/write your data (no auth). If that
  matters to you, we can add a simple Firebase Auth login later.
