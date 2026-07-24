# Bob's Detailing — What Changed (May 2026)

This is a summary of the SEO + lead-gen update made to your site. Read this before deploying so you know what to expect and what's still on your to-do list.

---

## TL;DR

- **Your existing 3 pages (index, packages, subscriptions) are visually 100% identical.** Nothing changed in the layout, animations, copy, pricing, or styling. The only changes are invisible additions inside the `<head>` and tracking parameters appended to booking links.
- **14 brand-new pages were added** in `/services/` and `/areas/` subfolders, plus a new `contact.html` and `about.html`. These are SEO-focused pages that didn't exist before.
- **A `sitemap.xml` and `robots.txt` were created** so search engines can discover everything.
- **Google Analytics 4 is now wired up across every page** with conversion tracking on Book Now buttons and phone clicks.

---

## Files Changed

### Existing files — surgical SEO additions only (NO visible changes)

| File | What was added |
|------|----------------|
| `index.html` | LocalBusiness JSON-LD schema, OG/Twitter meta tags, canonical URL, GA4 tracking, UTM params on 5 booking links, gtag click events on 4 Book Now buttons + 2 phone links |
| `packages.html` | Same head additions as above, UTM params on 6 booking links, gtag on 5 Book Now buttons + 1 phone link |
| `subscriptions.html` | Same head additions as above, UTM params on 3 booking links, gtag on 2 Book Now buttons + 1 phone link |

**Backup advice:** If you want a backup of the originals before this change, grab them from your git history (`git log` on the file should show the earlier version).

### New files — added to the project

```
UPLOAD-THESE-TO-GITHUB/
├── about.html                    [NEW]
├── contact.html                  [NEW]
├── sitemap.xml                   [NEW]
├── robots.txt                    [NEW]
├── README-WHATS-NEW.md           [this file]
├── services/                     [NEW SUBFOLDER]
│   ├── ceramic-coating.html
│   ├── paint-correction.html
│   ├── interior-detailing.html
│   ├── pet-hair-removal.html
│   ├── headlight-restoration.html
│   └── maintenance-detail.html
└── areas/                        [NEW SUBFOLDER]
    ├── pittsburgh.html
    ├── cranberry-township.html
    ├── wexford.html
    ├── sewickley.html
    └── mt-lebanon.html
```

Total: 14 new HTML pages + sitemap + robots.

---

## What's Different About the New Pages vs. Your Existing Site

The new pages use the **same design system** (Montserrat, sky/aqua/gold/navy palette, glass morph buttons, bubble decorations, etc.) so they feel like part of the same site. They don't have the unique animations from your original pages (van drive, bubble reveal, before/after sliders) — those stay exclusive to the pages you built.

The new pages have **their own nav** that includes dropdowns for Services and Service Areas. Your existing 3 pages **still have their original nav** unchanged.

> **Tradeoff to be aware of:** Visitors who land on your existing homepage won't see the new service/area pages in the nav. They'll only find them via Google search, social shares, or direct URL. Search engines will still rank these pages because:
> - They're listed in `sitemap.xml`
> - They cross-link to each other
> - They link back to your existing pages
>
> If you ever want to add nav links from the existing pages to the new ones, just say the word — it's a small additional change.

---

## What You Need To Do Before Deploying

### 1. Deploy everything in this folder
Push the entire `UPLOAD-THESE-TO-GITHUB/` folder to your hosting (GitHub → GoDaddy or wherever your site lives). The new `services/` and `areas/` subfolders will be created automatically when you push.

### 2. Verify GA4 is collecting data (after deploy)
1. Go to https://analytics.google.com
2. Open your Bob's Detailing property
3. Realtime → Overview
4. In another tab, visit your homepage and click around
5. You should see your visit appear in Realtime within ~30 seconds

Your Measurement ID `G-EPF4EF1DVM` is hard-coded into every page. If you ever change the GA4 property, you'll need to find/replace it across all 17 HTML files.

### 3. Submit your sitemap to Google Search Console (15 min)
1. Go to https://search.google.com/search-console
2. Add property: `bobsdetailingpgh.com` (Domain verification will require a DNS record at GoDaddy — Google walks you through it)
3. Once verified, go to Sitemaps in the left nav
4. Submit: `sitemap.xml`
5. Within a few days you should see "Discovered URLs" climb from 1 to ~16

### 4. Verify the OG image works for social sharing
The OG image is currently set to your `logo.png`. To test:
- Paste your homepage URL into https://www.opengraph.xyz/
- You should see a preview with the logo
- If you want a more eye-catching social preview later, create a `og-image.jpg` (1200x630px) with your van + branding and replace the `<meta property="og:image">` references with `og-image.jpg` instead of `logo.png`

### 5. Mark these as Key Events (conversions) in GA4
1. GA4 → Configure → Events
2. After your site has had a few visitors, you'll see these events appear:
   - `book_now_click`
   - `phone_click`
3. Click the toggle next to each to mark as a Key Event
4. This is what powers "How many bookings did this page drive?" reporting

---

## Things NOT Done in This Update (Your Call)

These items are in the original strategy script but require info or decisions only you can make:

- **Google Business Profile reclaim & optimization** — this is the highest-impact thing you can do. The strategy script (Part 2) walks through it. You need to start the reclaim process via business.google.com.
- **Fieldd review automation** — set up the SMS + email templates from Part 3 in your Fieldd dashboard. Triggers 2 hours after job completion.
- **og-image.jpg** — currently using logo.png as fallback. Create a custom 1200x630px image when you have time.
- **Bob's bio refinement** — the about page uses a story I drafted (10+ years detailing → launched LLC in 2024). If you want to swap it for a more personal version, edit the prose section in `about.html`.
- **Real-time customer reviews** — the new service & area pages reuse the 3 testimonials from your existing homepage. If you have more reviews, replace them in each new page (search for "Marcus T." to find them).
- **Adding nav links from existing pages → new pages** — your existing nav is unchanged. If you want me to add a small link or dropdown later so visitors discover the new pages, just say so.

---

## Quick Reference

| Item | Value |
|------|-------|
| Phone | (412) 925-8970 |
| Email | bookings@bobsdetailingpgh.com |
| Hours | 8am to 6pm, Monday thru Sunday |
| Contact / Quote form | https://www.bobsdetailingpgh.com/contact.html |
| GA4 ID | G-EPF4EF1DVM |
| Domain | https://www.bobsdetailingpgh.com |
| Pricing | Daily Driver $175 / Bob's Signature $275 / Showroom Shine $350 |

---

## SEO Improvements Summary

Before this update:
- 1 page indexed by Google (homepage)
- No structured data
- No social sharing previews
- No analytics on the marketing site
- No service-specific or location-specific landing pages

After this update:
- 16 pages submitted via sitemap
- LocalBusiness schema on every page (eligible for Google's local rich results)
- FAQ schema on every service & area page (eligible for FAQ rich snippets in search)
- Open Graph + Twitter cards on every page (rich previews on social shares)
- GA4 tracking on every page with conversion events
- 6 dedicated service landing pages targeting high-intent keywords ("ceramic coating Pittsburgh", "paint correction Pittsburgh", etc.)
- 5 dedicated area landing pages targeting local searches ("mobile car detailing Cranberry Township", etc.)
- Internal linking structure that distributes SEO authority across the site

**Realistic timeline to see lead-flow improvement:** 6–12 weeks. SEO is a lagging indicator. The GBP and review work (Parts 2 & 3 of the original strategy) will move faster — likely within 30 days.
