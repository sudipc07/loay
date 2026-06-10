# Loay Nofal — Consulting Profile Site

A single-page, static profile site for a Manufacturing Systems Architect.
Dark, brutalist/industrial aesthetic. No build step, no dependencies.

## Structure
```
index.html        All content + markup
css/main.css      Design tokens, brutalist grid, components, responsive
js/main.js        Mobile nav, scroll-reveal, contact-form handler
assets/           (favicon is inline SVG; drop self-hosted fonts here if desired)
docs/             Design spec
```

## Run locally
It's just files — open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy
Drop the folder on any static host — Netlify, Vercel, GitHub Pages, S3/CloudFront.
Nothing to compile.

## Wiring up the contact form (Formspree)
The form is **Formspree-ready** but not yet connected. Until an endpoint is added,
submitting shows a "form not yet connected" message instead of failing silently.

To connect it:
1. Create a form at https://formspree.io and copy your form ID.
2. In `index.html`, set the form's `action` (search for `id="inquiry-form"`):
   ```html
   <form class="inquiry-form" id="inquiry-form"
         action="https://formspree.io/f/YOUR_FORM_ID" method="POST" novalidate>
   ```
That's it — `js/main.js` will AJAX-submit to it and show success/error states.
(Any backend that accepts a `POST` with `Accept: application/json` works the same way.)

## Fonts
Loaded from Google Fonts (Barlow Condensed, Hanken Grotesk, JetBrains Mono).
To self-host, download the families into `assets/fonts/`, add `@font-face` rules,
and remove the `<link>` tags in `index.html`.

## Notes
- **No company names** and **no email** appear anywhere by design; contact is via
  the form only.
- Outcome figures are illustrative — update with final approved numbers before launch.
