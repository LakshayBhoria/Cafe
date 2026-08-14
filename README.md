# The Rock Café — Sonipat

A single-page site for The Rock Café (Sonipat Locality, Sonipat). Static HTML/CSS/JS — no build step, no dependencies.

## What's included

- Full one-page site: hero, about, menu (from the PDF), gallery, live-music schedule, reviews, order-online, contact/reserve, map.
- **Light / dark theme toggle** (top-right, sun/moon icon) — preference is saved in the visitor's browser.
- **Order Online** buttons for **Zomato** and **Swiggy** in the nav, hero, and a dedicated "Order It To Your Door" section.
- **Gallery** section with placeholder stock photos — swap these for real café photos before you go live (see below).
- Downloadable menu PDF (`rock-cafe-menu.pdf`).
- Embedded Google Map pointed at The Rock Café's coordinates, with a "Get Directions" link.
- Mobile-responsive, keyboard-accessible, reduced-motion friendly.

## Deploy to Vercel

**Option A — Vercel dashboard (no CLI needed)**
1. Go to [vercel.com/new](https://vercel.com/new) and choose "Add New… → Project".
2. Import this folder (drag-and-drop it, or push it to a GitHub repo first and import that repo).
3. Framework preset: choose **"Other"** (it's plain static HTML — no build command needed).
4. Click **Deploy**. Done — you'll get a live `*.vercel.app` URL in under a minute.

**Option B — Vercel CLI**
```bash
npm install -g vercel
cd rock-cafe
vercel        # first deploy, follow the prompts
vercel --prod # promote to production
```

Custom domain: once deployed, go to your project → **Settings → Domains** and add your own domain (e.g. `therockcafesonipat.com`) — Vercel handles the DNS/SSL steps for you.

## Before you go live — things to swap in

1. **Real photos** — the gallery (`#gallery` section) currently uses royalty-free stock photos as placeholders. Replace each `<img src="...">` in `index.html` with your own photos (drop image files into this folder and point the `src` at them, e.g. `src="gallery/the-deck.jpg"`).
2. **Phone / WhatsApp number** — search for `[add phone number]` and `910000000000` in `index.html` and replace with the café's real number (the WhatsApp float button uses the `wa.me/91...` link).
3. **Exact address** — search for `[add exact address]` and fill in the street address.
4. **Swiggy link** — the Swiggy button currently links to a search results page for "The Rock Cafe Sonipat" (`swiggy.com/search?query=...`) since a direct Swiggy listing URL wasn't available at build time. If the café has (or gets) a direct Swiggy restaurant page, replace that URL for a one-click experience like the Zomato button has.
5. **Zomato link** — already points to the café's real listing: `zomato.com/sonipat/the-rock-cafe-sonipat-locality/order`.
6. **Map** — the embedded map and "Get Directions" link use the coordinates from the café's Google Maps listing. Double check the pin is accurate once you're live.
7. **Reviews** — the three testimonials are placeholders; swap in real customer reviews.
8. **Reservation form** — currently just shows an on-page confirmation message (no backend). To actually receive bookings, wire the `<form class="reserve">` in `index.html` up to a form backend (e.g. Formspree, Getform) or route it to WhatsApp/email.

## File structure

```
rock-cafe/
├── index.html          — the whole site (HTML + CSS + JS, single file)
├── rock-cafe-menu.pdf  — downloadable menu
├── vercel.json          — Vercel config (clean URLs, caching headers)
└── README.md
```
