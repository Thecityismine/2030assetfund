# 2030 Asset Fund Deployment

This app is a static single-page site (`index.html`) and is ready to deploy to:
- GitHub (source control)
- Vercel (hosting)
- Firebase Hosting (optional second host)

## Prerequisites

- Git installed
- Node.js installed
- Firebase CLI (`firebase-tools`)
- Vercel CLI (`vercel`)
- Access to:
  - Firebase project `assetfund-86d80`
  - GitHub repo `https://github.com/Thecityismine/2030assetfund.git`
  - Vercel account

## 1. Initialize Git and push to GitHub

Run from this folder:

```powershell
git init
git branch -M main
git remote add origin https://github.com/Thecityismine/2030assetfund.git
git add .
git commit -m "Initial deploy setup (Firebase + Vercel)"
git push -u origin main
```

If `origin` already exists, use:

```powershell
git remote set-url origin https://github.com/Thecityismine/2030assetfund.git
```

## 2. Deploy to Vercel

`vercel.json` is already configured for static SPA routing + security headers.

First deploy:

```powershell
vercel
```

Production deploy:

```powershell
vercel --prod
```

## 3. Deploy to Firebase Hosting

`firebase.json` and `.firebaserc` are configured for project `assetfund-86d80`.

Login and deploy:

```powershell
firebase login
firebase deploy --only hosting
```

## 4. Firebase Auth domain allowlist

After Vercel deployment:

1. Open Firebase Console -> Authentication -> Settings -> Authorized domains
2. Add your Vercel domain (for example `2030assetfund.vercel.app`)
3. Add custom domain(s), if used

## Notes

- Firebase config and analytics are already embedded in `index.html`.
- This app is client-side only; no server build step is needed.
