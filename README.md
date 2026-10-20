# Montsong

Free ringtone catalog (Next.js + Bootstrap) with a built-in admin at `/admin`.

## Run
```
npm install
cp .env.example .env.local   # fill in values
npm run dev
```
Without the Firebase variables the site shows a sample catalog and `/admin` is a read-only preview.

## Firebase setup (5 minutes)
1. Firebase console > create a project > Build > Firestore Database > Create (production mode).
2. Project settings > Service accounts > Generate new private key.
3. Put `project_id`, `client_email`, `private_key` into `FIREBASE_PROJECT_ID`, `FIREBASE_CLIENT_EMAIL`, `FIREBASE_PRIVATE_KEY`.
4. Set `ADMIN_PASSWORD`.
5. Keep Firestore rules on deny-all (`allow read, write: if false;`). The server uses the admin key, so the browser never touches the database.

On Vercel, add the same four variables under Project > Settings > Environment Variables.

## How it works
- Latest Uploads on the home page reads published ringtones from Firestore.
- Download buttons go through `/api/download/<id>?f=mp3|m4r`, which counts the download and redirects to your Telegram/Drive link.
- The request form emails you through Formspree and also saves a copy to the admin dashboard.
- `/admin` shows stats, a 7-day downloads chart, ringtone management (add, publish/unpublish, delete) and requests.
"# Montsong-Ringtones" 
"# Montsong-Ringtones" 
"# Montsong-Ringtones" 
"# Montsong-Ringtones" 
