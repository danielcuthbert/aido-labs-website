# Aidō Labs Website

A placeholder landing page for Aidō Labs, hosted on Firebase Hosting.

## Setup Instructions

### 1. Create Firebase Project

```bash
# Install Firebase CLI if you haven't
npm install -g firebase-tools

# Login to Firebase
firebase login

# Create a new project (or use existing)
firebase projects:create aido-labs
```

### 2. Initialize Firebase Hosting

```bash
# From this directory
firebase init hosting

# Select:
# - Use an existing project: aido-labs
# - Public directory: public
# - Single-page app: No
# - GitHub Actions: Yes (optional, we have it configured)
```

### 3. Deploy Manually (First Time)

```bash
firebase deploy --only hosting
```

### 4. Set Up GitHub Actions (Automatic Deploys)

1. Generate a Firebase service account:
   ```bash
   firebase init hosting:github
   ```
   This will:
   - Create a service account
   - Add the secret to your GitHub repository

2. Or manually:
   - Go to Firebase Console → Project Settings → Service Accounts
   - Generate new private key
   - In GitHub repo → Settings → Secrets → Actions
   - Add `FIREBASE_SERVICE_ACCOUNT` with the JSON content

### 5. Custom Domain (Optional)

1. Go to Firebase Console → Hosting
2. Click "Add custom domain"
3. Follow DNS verification steps
4. SSL is automatic

## Local Development

```bash
# Preview locally
firebase serve --only hosting

# Opens at http://localhost:5000
```

## Project Structure

```
aido-labs-website/
├── public/
│   ├── index.html      # Main landing page
│   └── favicon.svg     # Site favicon
├── firebase.json       # Firebase hosting config
├── .firebaserc         # Firebase project config
└── .github/
    └── workflows/
        └── deploy.yml  # GitHub Actions workflow
```

## Costs

Firebase Hosting free tier includes:
- 10 GB storage
- 360 MB/day data transfer
- SSL certificate
- Global CDN

This should be free for a placeholder site.
# Trigger deploy
