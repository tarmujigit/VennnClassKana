# Kana Master

Mobile-first Hiragana & Katakana practice and testing app. Built with React + Vite and ready to upload to GitHub and deploy to Vercel.

## Current working features
- Responsive dark premium UI with orange accent.
- Hiragana/Katakana basic kana, dakuten/handakuten and yōon combinations.
- Multiple choice, typed answer, or mixed quiz.
- Kana → Romaji and Romaji → Kana question directions.
- Practice, timed exam, and retention/review modes.
- Randomized questions/options, score, accuracy, and response-time tracking.
- Per-character stats, weak kana list, session history, and CSV export.
- Student/teacher dashboard preview and local student profiles.
- Data persists in the current browser using localStorage.

## Deploy to Vercel
1. Upload this folder's contents to a new GitHub repository (not the ZIP itself).
2. In Vercel choose **Add New → Project**, import that GitHub repository.
3. Framework preset: **Vite**. Build command `npm run build`; output directory `dist`.
4. Deploy. No environment variables are needed for the local-only version.

## Important data note
This version saves data in the browser where it is used. It is a functional front-end MVP, not yet connected to Google Sheets or cross-device authentication. Browser data will not automatically sync between a student's phone and a teacher's computer.

To enable Google Sheets synchronization, add a server-side integration (for example Vercel serverless API routes with a Google service account) and real authentication/role authorization. Do not put Google service-account keys or spreadsheet write credentials in frontend code or GitHub. The current teacher view is a local prototype and is not secure for real student records.

## Suggested next integration step
- Create a Google Cloud service account and share the target spreadsheet with its service-account email.
- Store credentials as Vercel environment variables, never in repository files.
- Implement server-side API routes and authenticate users before returning or modifying data.
- Replace localStorage calls with authenticated API calls.
- Test authorization, rate limits, data validation, and concurrent writes before production use.

## Local development
```bash
npm install
npm run dev
```

The app is intended as a usable starter that can be deployed now, then connected to Google Sheets in a separate backend integration step. No claim is made that Google Sheets sync or secure real-user login is already implemented.
