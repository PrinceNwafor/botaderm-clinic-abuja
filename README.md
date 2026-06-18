# Botaderm Aesthetic Clinic — Abuja (Demo Preview)

A mobile-first, production-ready **demo preview** website for **Botaderm Aesthetic Clinic**
(@botadermclinic), an aesthetic & skincare clinic in **Abuja** (with a **Benin City** branch).

Built as pure **HTML + CSS + vanilla JavaScript** — no build step, no dependencies, no npm.
It is fast, SEO-aware, and designed so the clinic can view it, own it, and customise it.

> **Suggested route / slug:** `/botaderm-clinic-abuja`

---

## ▶️ Run it locally

It's a static site, so any static server works. Easiest options:

**Option A — just open the file**
Double-click `index.html`. (Most things work; videos and the map embed are happiest over `http://`.)

**Option B — local web server (recommended)**

```bash
# from inside the botaderm-clinic-abuja/ folder
python -m http.server 8000
```
Then open <http://localhost:8000/index.html>

(Other equivalents: `npx serve .` or the VS Code “Live Server” extension.)

## 🏗️ Build it

There is **no build step** — what you see is what ships. “Building” just means deploying the
folder as-is to any static host (GitHub Pages, Netlify, Vercel, Cloudflare Pages, etc.).

---

## 🗂️ Structure

```
botaderm-clinic-abuja/
├── index.html              One-page site: hero, branches, treatments, safety,
│                           before/after, gallery, stats, booking CTA, products,
│                           reviews, FAQ, location/map, footer.
├── book-appointment.html   4-step consultation booking → can send to WhatsApp.
│                           Branch selector (Abuja / Benin) + pre-visit intake.
├── css/style.css           Full design system. All brand colours live in :root.
├── js/main.js              Nav, reveal-on-scroll, FAQ, counters, booking engine,
│                           and the BOTADERM config block (phone / WhatsApp).
└── assets/
    ├── botaderm-logo.jpg   Logo (header, footer, favicon).
    ├── images/             Photos & before/after sets.
    └── videos/             Clip reels used in the hero and gallery.
```

---

## ✏️ Where to edit things (no coding needed for most)

| What you want to change | Where |
|---|---|
| **Logo** | Replace `assets/botaderm-logo.jpg` (keep the same name, or update the `<img class="brand-logo">` `src` in `index.html` + `book-appointment.html`, and the favicon `<link>` in `<head>`). A square image works best. |
| **Brand colours** | `css/style.css` → the `:root { … }` block at the very top. Change `--color-primary` (navy), `--color-accent` (gold), `--color-blue`. Everything else recolours automatically. |
| **WhatsApp / phone numbers** | `js/main.js` → the `BOTADERM = { … }` block at the top. Set `whatsapp`, `whatsappAbuja`, `whatsappBenin` (international format, digits only, e.g. `2348012345678`). Also update the `tel:` numbers in the top bar / footer. |
| **Prices (incl. Mounjaro)** | `index.html` → the “Treatment Menu” section (`#menu-skin`, `#menu-weight`). Replace `₦ —` with real prices. |
| **Photos / before & after** | Drop new files into `assets/images/` and point the `src=` at them. Add as many before/after `ba-card` blocks as you like. |
| **Videos** | Drop new `.mp4`s into `assets/videos/` and update the `<video src=>`. |
| **Branch addresses & map** | `index.html` → the “Find Us” (`#contact`) section: edit the `[Suite / Street address]` text and the two Google Maps `<iframe src>` (replace with the real embed link from Google Maps → Share → Embed). |
| **HMO / insurance details** | `index.html` → FAQ section (“Do you accept HMO or insurance?”). |
| **Doctor names / credentials** | `index.html` → “Safe Hands” section and reviews — add real names and qualifications. |
| **Clinic name / tagline / hours** | Search the HTML for `Botaderm`, `Mon–Sat`, and the footer tagline. |
| **Remove the PREVIEW banner** | Delete the `<div class="demo-ribbon">…</div>` at the top of each HTML file when going live. |

### Connecting the booking form to a real system
The booking flow is **front-end only**. On confirm it builds a pre-filled **WhatsApp** message
(routed to the chosen branch line) so no booking is lost. To also save bookings to a backend,
see `initBooking()` in `js/main.js` and replace the simulated confirm with a real `fetch()` POST
to your endpoint / scheduling API / email service.

---

## ✅ What's included (matches the brief)

- **Hero** with a Botaderm-specific promise + clear CTAs: **Book Appointment**, **Chat on WhatsApp**, **View Services**.
- **Branch selector** — Abuja (flagship) & Benin City, so clients choose the right location.
- **Premium treatment menu** — Acne, peels, laser resurfacing, non-surgical aesthetics, and
  medically-supervised weight loss (with real Mounjaro guide pricing).
- **Safety / qualification trust block** — medically supervised, trained practitioners, sterile rooms, genuine products.
- **Before/after gallery** (real results + placeholder for more).
- **Visual gallery** (photos + video clips).
- **Consultation booking** + automated **pre-visit intake** + WhatsApp hand-off.
- **Product inquiry** area (skincare products via WhatsApp).
- **Reviews**, **FAQ** (incl. HMO/pricing/safety), **Location/Map**, and a **footer**.
- **SEO**: title/description around “Aesthetic / skincare clinic in Abuja”, Open Graph tags,
  and `MedicalClinic` structured data (JSON-LD).
- **Mobile-first & fast**: responsive grids, lazy-loaded images, no horizontal scroll.

> Photos, prices, HMO details, doctor names and final brand corrections are all placeholders/guides — easy to replace.
