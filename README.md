# Treelink

[Try out→](treelink-ops.vercel.app)


Treelink is a static web application for creating a public link page from one account. Users sign in with Google, manage links from a dashboard, and share a public profile URL.

## What this project includes

1. Landing page with Google sign in
2. Authenticated dashboard for profile and link management
3. Public profile page with click tracking
4. Privacy Policy page
5. Terms of Service page
6. Contact page

## Core functionality

1. Firebase Authentication with Google provider
2. Firestore user document creation on first sign in
3. Link create, update, delete, and reorder in dashboard
4. Username based public profile route using query parameter `profile.html?u=<username>`
5. Per link click count tracking on public profile
6. Theme color, bio, display name, username, and profile photo settings

## Tech stack

1. HTML
2. CSS
3. Vanilla JavaScript
4. Firebase App SDK compat
5. Firebase Auth SDK compat
6. Firebase Firestore SDK compat

## Project files

1. `index.html` for landing and authentication entry
2. `dashboard.html` for authenticated link and profile management
3. `profile.html` for public user profile and link clicks
4. `privacy.html` for privacy policy
5. `terms.html` for terms of service
6. `contact-us.html` for contact methods

## Firebase data model

Collection `users`

Document `users/{uid}` fields

1. `uid`
2. `name`
3. `email`
4. `photoURL`
5. `username`
6. `theme`
7. `bio`
8. `createdAt`

Subcollection `users/{uid}/links`

1. `title`
2. `url`
3. `icon`
4. `clicks`
5. `order`
6. `createdAt`

## Local run instructions

1. Clone this repository.
2. Open the project folder.
3. Serve the folder with any static server.
4. Open `index.html` in your browser.

Example with Node.js `serve`

```bash
npx serve .
```

## Firebase setup

1. Create a Firebase project.
2. Enable Google sign in in Authentication.
3. Create a Firestore database.
4. Add your web app and copy Firebase config.
5. Replace `firebaseConfig` in `index.html`, `dashboard.html`, and `profile.html`.

## Notes

This project currently uses inline CSS and inline JavaScript in each page. All pages are standalone and can be hosted as static files.

## License

No license file is included in this repository yet.
