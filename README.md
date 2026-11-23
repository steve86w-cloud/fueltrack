# FuelTrack V7 — Optional AI Meal Analyser & Nutrition Coach

## Included
- **V7 PWA** with all V6 features, barcode scanner, local 107-food reference library and existing `fueltrack-v2` local storage retained.
- **AI Analyse** for typed/dictated descriptions or a resized food photograph, with a review screen before logging.
- **AI nutrition coach** using today's diary totals and goal summary. Conversations are not saved.
- **Cloudflare Worker** in `worker/` for secure server-side AI provider calls.
- Without a configured Worker, **offline estimate still works**. A genuine AI response only works after the Worker is deployed and funded with an API account.

## Update GitHub Pages
1. Export a backup in FuelTrack settings on your phone.
2. Replace **only** `index.html` and `sw.js` in your existing GitHub repository with the files in the root of this ZIP. Do **not** upload `worker/` to the public repository: keep backend code in your own Cloudflare Worker project.
3. Commit changes, reload the hosted site, reopen FuelTrack on your Pixel 8a; look for V7.

## Connect optional AI — not free API usage
1. Create a Cloudflare account and a **Worker** named `fueltrack-ai` using the JavaScript from `worker/src/index.js` (via Dashboard code editor or Wrangler). For CLI: `cd worker`, then `npx wrangler deploy` (requires Node/npm and Cloudflare authentication). Edit `worker/wrangler.toml` ALLOWED_ORIGIN if your GitHub username is different.
2. In the Worker dashboard **Settings → Variables and Secrets**, add two **encrypted secrets**: `OPENAI_API_KEY` (API key created in your provider's API account) and `FUELTRACK_ACCESS_TOKEN` (your own strong, random private password/token, unrelated to the API key). NEVER add either secret to GitHub or JavaScript in `index.html`.
3. In FuelTrack **Settings → Optional AI connection**, paste the Worker HTTPS URL and the personal `FUELTRACK_ACCESS_TOKEN`, save and Test connection.
4. Open Smart log, describe food or take a picture, tap **AI analyse**, verify the estimate and save. Open **AI coach** from Today to ask a question.
5. Keep API billing limits low and monitor usage. An access token is needed, but this is a single-user prototype, not a hardened public SaaS authentication system. CORS alone is **not** a security boundary. Rotate the access token if it is exposed.

## Privacy and limits
- AI requests send your text or reduced photo and, for coach, a minimal diary summary to your Cloudflare Worker and AI provider. They do not upload your whole diary by default.
- The Worker requests `store:false` for provider responses. This is not a promise of zero provider logging; review provider retention policies.
- The personal Worker access token and URL are stored in local browser storage on the phone and are **not** included in FuelTrack nutrition backups.
- Photos are not saved to the diary or GitHub.
- Calorie estimates from photos are particularly uncertain; confirm portions and labels before logging.
- The existing GitHub Pages site is free; provider AI API calls can cost money. No costs until you choose to set up a paid API account.
