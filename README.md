# katpencilportraits.com

Single-page portrait gallery site for **Katia Chalin** — hand-drawn pencil portrait artist.

Deployed at: https://katpencilportraits.com

## Stack

- Static HTML/CSS/JS (no build step)
- Hosted on Cloudflare Pages (project `katpencilportraits`)
- DNS on Cloudflare (zone `katpencilportraits.com`)
- Domain registered at GoDaddy (Cloudflare nameservers)
- Email alias `kat@katpencilportraits.com` → `katpencilportraits@gmail.com` via Cloudflare Email Routing

## Layout

```
site/
  index.html        ← Single-page site (gallery, about, contact)
  img/              ← Gallery photos (photo-01.jpg ... photo-11.jpg)
  robots.txt
  sitemap.xml
  _headers          ← Cloudflare Pages headers config
```

## Editing the site

Tell Claude: **"update the kat pencil portraits site to [change]"** and Claude follows the same pattern as every other repo in the portfolio.

### To add or remove a photo

1. Drop the new image into `site/img/` (use the convention `photo-12.jpg`, `photo-13.jpg`, …)
2. Edit the `photos` array near the bottom of `index.html`, add `{ src: '/img/photo-12.jpg', alt: '...' }`
3. Commit + push to `main` → Cloudflare Pages auto-deploys.

### To change copy / colors / typography

Edit `index.html` directly. CSS lives at the top of the file inside `<style>`. Colors are defined as CSS variables in `:root`:

| Variable | Use |
|---|---|
| `--ink` | Body text, primary buttons |
| `--paper` | Page background |
| `--paper-warm` | Section background (about, contact card) |
| `--accent` | Italic accents, eyebrow text |

### Phone number

The site does not currently include a phone number (none was provided at launch). To add one, edit the contact section in `index.html` and add a third `<a class="contact-link">` with `tel:`.

## Deploys

- Auto-deploy via Cloudflare Pages on every push to `main`.
- Branch deploys auto-publish at `<branch>.katpencilportraits.pages.dev`.

## License

Site code: © Nathan Poole / Fabrhana Investments LLC.
Artwork in `site/img/`: © Katia Chalin. All rights reserved.
