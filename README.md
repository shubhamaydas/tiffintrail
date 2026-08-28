# Tiffin Trails — Website Launch Package

A complete, self-contained landing page for tiffintrail.com, built around the
brand's own product: the returnable steel tiffin carrier.

## What's in this folder

```
tiffintrail-website/
├── index.html          ← the full site (HTML + CSS + JS, single file, no build step)
├── README.md            ← this file
└── assets/
    ├── logo-mark.svg    ← icon only (stacked tiffin carrier), for app icons/social avatars
    ├── logo-lockup.svg  ← icon + wordmark, for use outside the site (decks, emails, print)
    └── favicon.svg       ← simplified icon, already wired up in index.html
```

`index.html` has zero dependencies except two Google Fonts pulled over a CDN
link in the `<head>`. Open it directly in a browser, or upload the whole
folder to any static host (see **Deploying**, below).

## Design system

**Concept:** every element is grounded in the steel tiffin carrier (dabba) —
its stacked tiers, its clasp bar, and the routing-code system Mumbai's
dabbawalas have used for over a century to get a home-cooked lunch to the
right desk without a single digital tool. That's also where the "trail code"
on each menu item comes from (`TT-04-NV` etc.) — a wink at the real dabbawala
coding system, and the brand name.

**Colours** (see `:root` in `index.html` for the full token list):
| Token | Hex | Use |
|---|---|---|
| `--ink` | `#23201B` | Text, dark sections |
| `--paper` | `#E7E2D3` | Page background |
| `--steel` | `#9AA39B` | Tiffin-tier grey, dividers |
| `--turmeric` | `#D9A02C` | Primary accent, CTAs |
| `--curry` | `#4B6043` | Secondary accent, dark band |
| `--veg` / `--brick` | `#2F6B33` / `#9C3B24` | FSSAI-style veg/non-veg marks |

**Type:**
- **Bricolage Grotesque** (display/headlines) — a characterful grotesk with a bit of bounce, used bold and large.
- **Public Sans** (body copy) — clean and highly legible at small sizes.
- **IBM Plex Mono** (labels, trail codes, stencil-style eyebrows) — gives the stenciled, industrial feel of paint on a tin lid.

All three are open-license (SIL Open Font License) and loaded free from Google Fonts — no licensing cost or attribution requirement beyond what's already in the font files.

**Signature element:** the "clasp divider" between sections (a thin bar with a
circular loop) mimics the metal clasp that holds a tiffin carrier's tiers
together — used instead of a generic `<hr>`.

## Photography

All photos are sourced from [Unsplash](https://unsplash.com) and used under the
[Unsplash License](https://unsplash.com/license) — free for commercial use,
no permission or attribution legally required. Credit is listed below anyway,
since it's good practice and keeps a record of where each image came from if
you ever need to swap one out.

| Section | Photographer | Unsplash profile |
|---|---|---|
| Palak Paneer | Deepal Tamang | @deepal_tamang |
| Dal Makhani | Bruna Branco | @brunabranco |
| Butter Chicken | amirali mirhashemian | @amir_v_ali |
| Hyderabadi Biryani | Mario Raj | @chefmariii |
| Chole Bhature | Jaydeep Gajera | @jaydeepgajera |
| Aloo Gobi | Zoshua Colah | @zoshuacolah |
| Rajma Chawal | Sumeet B | @pixel_is_fun |
| Kadai Paneer | Nisha Ramesh | @nisharamesh |
| Sambar Rice | Ananthan Chithiraikani | @ananthan8110 |
| Methi Thepla | Lior Shapira | @shapira |
| Hero gallery / steel plate | Zoshua Colah | @zoshuacolah |
| Hero gallery / food spread | Perspective Studio | @perspectievstudio |
| Hero gallery / rice on plate | Saktheeswaran Govindarajan | @saktheeswaran_g |
| Cooks section / cooking pot | Sanket Shah | @sanketshah |
| About & spices photos | Anju Ravindranath | @anjurnath |

Before launch, consider swapping in your own kitchen and cook photography —
real photos of your actual cooks and dishes will always convert better than
stock imagery, even good stock imagery.

## Before you launch — things to update

1. **Social links** — Instagram, Facebook, and WhatsApp icons in the footer currently point to `#`. Replace with your real profile URLs once they exist.
2. **Waitlist form backend** — the form currently shows a "You're on the trail" success message but doesn't send data anywhere. Wire it to a real service before launch, e.g.:
   - [Formspree](https://formspree.io) or [Getform](https://getform.io) — fastest, no backend needed, just change the form's `action` attribute.
   - Mailchimp / ConvertKit / Brevo — better if you want the list to feed straight into your email marketing tool.
3. **Legal pages** — Privacy, Terms, Cookies, and Allergen Info links in the footer point to `#`. Even a simple one-page policy is worth having live before you collect emails (GDPR applies since the entity is registered in Germany).
4. **OG/social preview image** — `index.html` has Open Graph meta tags (title, description, url) but no `og:image` yet. A 1200×630px image (you can adapt the hero illustration in `assets/logo-lockup.svg` as a starting point) makes shared links look far better on WhatsApp/social.
5. **Domain email** — footer links to `hello@tiffintrail.com`; make sure that inbox exists before launch.
6. **Stock photography** — see the Photography section above. All images are free and legally clear to use, but swapping in real photos of your own kitchens, cooks, and dishes before launch will make the site feel authentic rather than generic.

## Deploying

This is a static site — no server or database required. Simplest free options:

- **Netlify / Vercel** — drag the whole folder into their web dashboard, or connect a GitHub repo. Both give you `tiffintrail.com` DNS instructions.
- **GitHub Pages** — push this folder to a repo and enable Pages in settings.
- **Cloudflare Pages** — same idea, with very fast global delivery.

All of these have generous free tiers that comfortably cover a pre-launch waitlist page.

## Accessibility & performance notes already built in

- Semantic HTML throughout (`<nav>`, `<main>`, `<section>`, `<footer>`, labelled form fields).
- Visible focus outlines on every interactive element (`:focus-visible`).
- `prefers-reduced-motion` respected — animations and smooth-scroll disable automatically for users who've asked their OS to reduce motion.
- Fully responsive from ~360px mobile up through desktop, with a proper mobile nav.
- No render-blocking scripts; the one inline `<script>` only handles the mobile menu, scroll-reveal, and form UI — nothing that affects initial paint.
