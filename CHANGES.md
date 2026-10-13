# What changed from the old site

## Replaced
- **Home page.** The old single-page direct-to-business site is now the agency site. The old page lives on at `/for-local-businesses`.
- **Navigation.** Old: What we fix, How it works, Pricing, FAQ, Client Login, Get your free audit. New: How it works, Safety, Pricing, FAQ, About, Start a free pilot.
- **Tech.** Tailwind CDN script removed (it is not meant for production). Now plain CSS, system font stack, Vite build.
- **Brand assets.** The logo and favicon PNGs had a gray vignette baked in and weighed about 590 KB and 540 KB. I cut the mark out onto a transparent background in flat Alpine green. Same artwork, now about 28 KB and 3 KB, plus a light version for the dark footer. This also changes the logo on the legacy pages, Privacy, Terms and portal, which use the same file names.
- **Palette.** The old site used oat, deep forest and honey tones that were close to, but not exactly, your palette. The new site uses your exact six colors.
- **Contact and form.** Same email and same Formspree endpoint. New pilot form fields. Old audit form is only on the legacy page.

## Removed from the new site (not deleted, still on the legacy page)
- Direct-to-business pricing ($179.99 per month, $199.99 setup, $99.99 Yelp and Facebook add-ons).
- **Client Login** link. The portal pages still exist at their old addresses and were copied into `public/portal/` unchanged, so existing clients can still sign in, but nothing on the new site links to them.
- Before and after card (3.8 to 4.7 stars) and the "2 to 18 reviews, 12% to 93% responses" numbers. These break the new honesty rules. They remain on the legacy page, labeled as illustrative. **I recommend removing them there too.**
- Cookie banner. The new site sets no cookies and has no analytics.

## Kept
- Name, domain, logo artwork, Lens and Ladder footer line, Privacy, Terms and Cookie links.

## Added
- Safety, Pilot, About pages, approval queue illustration, Open Graph image, JSON-LD organization data on the home page, one small link on the legacy page back to the agency site.

## Decide
- The legacy page and portal still depend on Tailwind's CDN script and Supabase. I did not touch them.
- The portal's `supabase-client.js` contains Supabase's public (anon) key. That is by design and its own comment says access is enforced by row level security, but make sure RLS is on.
