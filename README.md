# JJeff Development LLC — website

Static site (no build step) for jjeffdevelopment's public business site — built
primarily to give Apple's D-U-N-S / business verification something real and
checkable to find.

Domain: **www.jjeff.app** (see `CNAME`). Contact form: [Formspree](https://formspree.io/f/mppznbpb),
wired up via `@formspree/ajax`.

## Before this is "live" and verification-ready

- [ ] **DNS** — point `jjeff.app` at GitHub Pages (see below). Nothing is
      live at the domain until this is done.
- [ ] **Legal business details** — the footer currently just says "Cleveland,
      Ohio". If Apple/D&B verification wants a registered address, add it to
      the footer in `index.html`.
- [ ] **Push to GitHub + enable Pages** — see below.

## Deploy on GitHub Pages

1. Push this repo to GitHub (public repo, since Pages needs it — or a private
   repo if you're on GitHub Pro/Team/Enterprise).
2. Repo **Settings → Pages** → Source: **Deploy from a branch** → Branch:
   `main` / `/ (root)`. The `CNAME` file already in this repo tells GitHub
   the custom domain is `www.jjeff.app` — Settings → Pages should pick it up
   automatically.
3. At your domain registrar/DNS provider for `jjeff.app`, add:
   - four `A` records for the apex (`@`) pointing at GitHub's Pages IPs:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - a `CNAME` record pointing `www` at `<yourusername>.github.io`
   (GitHub will redirect the apex `jjeff.app` to `www.jjeff.app` once both
   are set, since the `CNAME` file names `www` as canonical.)
4. Enable **Enforce HTTPS** once the cert provisions (can take a few minutes
   to an hour after DNS propagates).

## Structure

```
index.html          page content
css/style.css       all styling
assets/projects/    project icons used in the "Upcoming projects" section
CNAME               GitHub Pages custom-domain config (www.jjeff.app)
```
