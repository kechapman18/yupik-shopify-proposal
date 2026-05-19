# Yupik × Shopify Plus — Merchant Proposal Site

A password-protected single-page proposal for Brahim Abdelkader (Yupik / Toolsi), recapping the May 19, 2026 discovery call.

**Live site:** [GitHub Pages URL after deploy]
**Password:** shared separately with the merchant

## How it works

Content is AES-GCM encrypted with a key derived from the password (PBKDF2, 250k iterations). Decryption happens client-side in the browser. Without the password, the page shows only the gate.

## Local files (gitignored)

- `src/content.html` — the merchant-facing content (unencrypted source)
- `src/template.html` — the password gate shell with decryption JS
- `src/style.css` — styles
- `build.js` — encrypts content + writes `docs/index.html`

## Rebuild after editing content

```
node build.js <password>
```

Then commit and push. GitHub Pages serves `/docs/index.html`.
