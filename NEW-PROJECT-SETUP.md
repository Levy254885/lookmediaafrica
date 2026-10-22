# LookMedia Africa — setup for a new project

This is the TrendSpot codebase rebranded as **LookMedia Africa** (lookmediaafrica.co.ke).

## What changed
- Name / domain: every "TrendSpot" and "trendspot.co.ke" is now "LookMedia Africa" / "lookmediaafrica.co.ke"
  (wordmark, footer, admin, metadata, legal pages, sitemap/robots, Cloudinary folders `lookmediaafrica/...`).
  Central values live in `src/lib/constants.ts` (SITE_NAME, SITE_DOMAIN, SITE_URL).
- Colours (edit in `src/app/globals.css`, `:root` and `@theme inline`):
  - Sky blue `#0ea5e9` (`--sky`) – rules, underlines, highlights, accents on black
  - Deep sky `#0369a1` (`--accent`) – text links, kickers, buttons (readable on white)
  - Maroon `#7f1d2d` (`--maroon`) – breaking ticker, hover on buttons, errors/delete
  - Black, white and greys unchanged
- Fonts and layout are unchanged.

## Make it a brand-new project (do NOT reuse TrendSpot's data)
1. Create a NEW Firebase project: Firestore (production mode), Authentication → Email/Password.
2. Create a NEW Cloudinary upload preset (unsigned) — or reuse your cloud with the new `lookmediaafrica/` folders.
3. Copy `.env.example` → set the variables in Vercel (new project) — all `NEXT_PUBLIC_FIREBASE_*`,
   `FIREBASE_SERVICE_ACCOUNT_JSON` (or `FIREBASE_ADMIN_*`), `ADMIN_EMAILS`,
   `NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME`, `NEXT_PUBLIC_CLOUDINARY_UPLOAD_PRESET`, `NEXT_PUBLIC_SITE_URL=https://lookmediaafrica.co.ke`.
4. Publish `firestore.rules` (deny-all) in Firebase → Firestore → Rules.
5. Deploy, sign in at `/admin/login`, then Settings → Import sample articles (or write your own).

## Things to review by hand
- Copy in `src/app/about`, `privacy`, `terms`, `disclaimer`, `contact` still describes the old publication's focus — edit to suit.
- Seed articles (`src/data/seed.ts`) are sample content only.
- Navigation / categories: `src/lib/constants.ts`.
