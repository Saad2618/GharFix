# GharFix — Home Services Website

## Files in this package

```
gharfix/
├── index.html      ← Complete website (single file)
├── sitemap.xml     ← SEO sitemap (update URLs after deployment)
├── robots.txt      ← Search engine instructions
└── README.md       ← This file
```

---

## Before going live — checklist

### 1. Replace the WhatsApp number
Search for `923001234567` in `index.html` and replace with your actual number (country code + number, no spaces or +).
Also update in `sitemap.xml` and `robots.txt` the domain `gharfix.pk` if your domain differs.

### 2. Replace the email
Search for `hello@gharfix.pk` and update to your real email address.

### 3. Set your real domain
In `index.html`, update the canonical and Open Graph URLs:
```html
<link rel="canonical" href="https://YOURDOMAIN.pk/" />
<meta property="og:url" content="https://YOURDOMAIN.pk/" />
```
Also update all `https://gharfix.pk/` references in `sitemap.xml`.

### 4. Add an OG image
Create a 1200×630px image and place it at `/images/og-image.jpg`.
This appears when someone shares your link on WhatsApp, Facebook, etc.

### 5. Upload sitemap to Google Search Console
After deployment, submit `https://YOURDOMAIN.pk/sitemap.xml` in Google Search Console.

---

## Deployment options (free)

| Platform     | Steps                                                              |
|--------------|--------------------------------------------------------------------|
| **Netlify**  | Drag and drop the `gharfix/` folder at netlify.com/drop           |
| **Vercel**   | `npm i -g vercel` → `vercel` inside the folder                    |
| **GitHub Pages** | Push to repo → Settings → Pages → Deploy from branch         |
| **cPanel hosting** | Upload files via File Manager to `public_html/`           |

---

## Adding new services later

To add a new service card, copy any `<article class="service-card">` block inside the `services-grid` div and update:
- The emoji in `.service-icon`
- The `h3` heading (English `data-en` + Urdu `data-ur`)
- The `p` description
- The WhatsApp link `href` (change the `text=` parameter)
- The `.service-link` label

The grid auto-flows — no layout changes needed.

---

## Changing the WhatsApp number across the whole site

Do a find-and-replace for `923001234567` → your number in `index.html`.

---

## Language system

The site uses a `data-en` / `data-ur` attribute system. Every visible text element has both attributes. The JS `setLang()` function swaps them on toggle. To translate a new element:

```html
<p data-en="Your English text" data-ur="آپ کا اردو متن">Your English text</p>
```

---

## SEO maintenance tips

- Update `<lastmod>` in `sitemap.xml` whenever you make content changes.
- When adding city-specific pages in future (e.g. `/karachi/plumbing/`), add them to `sitemap.xml`.
- Add Google Analytics or similar by pasting the tracking script before `</head>`.
