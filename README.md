# Treelink

A lightweight, modern link aggregation platform built with vanilla web technologies and Firebase.

## Overview

Treelink allows users to create a personalized public profile page that hosts multiple links from a single URL. Share your social media, portfolio, store, newsletter, and more in one beautifully designed location.

**Live Demo:** [treelink-ops.vercel.app](https://treelink-ops.vercel.app)

## Features

- **Google Sign-In** – Quick authentication via Google
- **Dashboard** – Manage links and profile settings
- **Public Profiles** – Share a unique username-based link
- **Link Management** – Create, edit, delete, and organize links
- **Click Tracking** – Monitor link performance in real-time
- **Customization** – Profile photo, display name, bio, custom theme color
- **Light/Dark Modes** – Automatic theme detection with user preferences
- **Mobile-Friendly** – Responsive design for all devices

## Tech Stack

- HTML5
- CSS3 (Variables, Animations, Responsive Grid)
- Vanilla JavaScript (ES6+)
- Firebase Authentication (Google)
- Firebase Firestore (Database)

## File Structure

```
├── index.html           Landing page & authentication
├── dashboard.html       Link & profile management
├── profile.html         Public profile sharing
├── contact-us.html      Contact form
├── privacy.html         Privacy policy
├── terms.html           Terms of service
└── README.md
```

## Getting Started

### Prerequisites
- Modern web browser
- Google account (for testing authentication)
- Firebase project

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/treelink.git
   cd treelink
   ```

2. **Configure Firebase**
   - Create a Firebase project at [firebase.google.com](https://firebase.google.com)
   - Set up Firebase Authentication (Google provider)
   - Enable Firestore Database
   - Copy your Firebase config credentials

3. **Update Firebase Configuration**
   - Located in `index.html`, `dashboard.html`, and `profile.html`
   - Replace placeholder credentials with your project values

4. **Deploy**
   - Traditional hosting: Vercel, Netlify, GitHub Pages
   - Local testing: `python -m http.server 8000`

## Database Schema

### Collection: `users`

Document structure (`users/{uid}`):
```javascript
{
  uid: string,
  email: string,
  displayName: string,
  username: string (unique),
  bio: string,
  photoURL: string,
  themeColor: string (hex),
  links: object {
    [linkId]: {
      title: string,
      url: string,
      clicks: number
    }
  },
  createdAt: timestamp,
  updatedAt: timestamp
}
```

## User Workflow

1. **Sign In** → Google authentication on index.html
2. **Setup** → Configure username, display name, bio, photo
3. **Manage Links** → Create/edit/reorder links from dashboard
4. **Share** → Send public profile URL to audience
5. **Track** → Monitor link clicks in dashboard

## Public Profile URL Format

```
profile.html?u=username
```

Example: `https://example.com/profile.html?u=john_doe`

## Development

### Adding New Features

- Links are stored as objects in the user document
- Theme colors are applied dynamically via CSS variables
- Both light and dark themes are supported
- Animations use CSS transitions and keyframes

### Code Organization

- Global styles use CSS custom properties (--accent, --bg, --text, etc.)
- Responsive breakpoints at 900px and 1200px
- Firebase initialization in each HTML file
- Authentication state managed per page

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Android)

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

## License

MIT License – feel free to use this project for personal or commercial purposes.

## Support & Feedback

Found a bug? Have a suggestion? Please open an issue or contact us via the contact page.

---

Built with care for creators and businesses.
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
