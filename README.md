# OWL WEAR — SS 2026

Self-contained static storefront for OWL WEAR. Everything (HTML, CSS, JS, and
images) lives inside a single `index.html` file, so there is **no backend and
nothing to build** — GitHub Pages serves the file directly.

## What's in the box

- **Storefront** — hero, collections, product pages, size finder, reviews, cart,
  wishlist. Cart & wishlist persist in the visitor's browser (localStorage).
- **Built-in admin panel** — no separate app. Edit content in the browser and
  re-publish. See below.

## Admin panel — how to edit the site

1. Open the live site and scroll to the footer (or use the admin link/passcode
   prompt). Enter the **admin passcode** (default: `owl2026`).
2. Edit hero text, products, prices, size chart, countdown, etc. Changes show in
   a live preview instantly.
3. Press **⬇ Publish — Download index.html**. Your browser downloads a fresh
   `index.html` containing all your edits.
4. Upload that file to this repo (replace the existing `index.html`, commit).
   The live site updates within ~1 minute.

> Change the passcode from the admin **Settings** tab, then Publish. The passcode
> is stored in the published file — it deters casual visitors but is **not
> strong security**, so don't treat it as a real login.

## Hosting (GitHub Pages)

This repo is set up to be served by GitHub Pages:

1. Go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Select the branch this file lives on and the `/ (root)` folder, then **Save**.
4. After a minute, your site is live at `https://<user>.github.io/<repo>/`.

## Custom domain (Hostinger)

The `CNAME` file in this repo tells GitHub Pages which domain to serve. To point
your Hostinger domain at GitHub Pages, add these DNS records in Hostinger
(**hPanel → Domains → DNS / Nameservers → DNS Zone**):

**Apex/root domain** (`example.com`) — four `A` records:

| Type | Name | Points to        |
|------|------|------------------|
| A    | @    | 185.199.108.153  |
| A    | @    | 185.199.109.153  |
| A    | @    | 185.199.110.153  |
| A    | @    | 185.199.111.153  |

**www subdomain** — one `CNAME`:

| Type  | Name | Points to               |
|-------|------|-------------------------|
| CNAME | www  | `<user>.github.io`      |

Then in **GitHub → Settings → Pages → Custom domain**, enter your domain, save,
and tick **Enforce HTTPS** once the certificate is issued (can take up to an
hour). DNS changes can take a little while to propagate.
