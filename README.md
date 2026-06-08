# Israel Alalibo — Trading Portfolio

A fast, mobile-first personal portfolio for a funded trader. Built as a clean
static site (HTML + CSS + vanilla JS) — **no build step**, deploys to Vercel in
seconds.

🔗 **Live:** _add your Vercel URL here once deployed_

---

## ✨ What's inside

- **Hero** with portrait, headline stats and dual call-to-action.
- **Animated stat counters** (payouts, evaluations, certificates, compliance).
- **About** — your story and risk-first philosophy.
- **Approach** — six cards covering your risk-management framework.
- **Track record timeline** — every milestone from evaluation to payout.
- **Verified proof** — a gallery of your real certificates with a click-to-zoom lightbox.
- **Contact** — email, phone, Instagram + a working contact form.
- **Mobile-first** throughout, with a floating "Get in touch" button on phones.

---

## 📁 Structure

```
TradingPortfolio/
├── index.html              # the whole page
├── assets/
│   ├── css/styles.css      # all styling (mobile-first)
│   ├── js/main.js          # nav, counters, reveals, lightbox
│   ├── favicon.svg
│   └── img/                # optimised photos + certificates (deployed)
├── vercel.json             # caching + security headers
├── .gitignore
└── README.md
```

> The original `pictures of me/` and `certificates/` folders are **git-ignored**
> (kept on your machine only). The web-ready versions live in `assets/img/`.

---

## 🖥️ Preview locally

From the project folder:

```powershell
# Option A — Python (already installed)
python -m http.server 5500
# then open http://localhost:5500

# Option B — Node
npx serve .
```

---

## ✉️ Activate the contact form (1 minute, free)

The form uses [FormSubmit](https://formsubmit.co) — no account or API key needed.

1. Deploy the site (below) **or** preview locally.
2. Fill in the form once and hit **Send**.
3. FormSubmit emails you a confirmation link **the first time only** — click it.
4. Done. Every future submission lands in `israelalalibo97@gmail.com`.

Want submissions to redirect to a thank-you page? Add this hidden field inside
the `<form>` in `index.html`:

```html
<input type="hidden" name="_next" value="https://YOUR-DOMAIN/thanks.html" />
```

If you ever prefer no third party at all, change the form to a simple `mailto:` —
ask and it's a two-line change.

---

## 🚀 Deploy: GitHub → Vercel

### 1. Create the GitHub repo

```powershell
cd c:\TradingPortfolio
git init
git add .
git commit -m "Initial commit: trading portfolio"
git branch -M main
```

Create an empty repo on GitHub (e.g. `trading-portfolio`), then:

```powershell
git remote add origin https://github.com/<your-username>/trading-portfolio.git
git push -u origin main
```

> Using the GitHub CLI? It's a one-liner:
> `gh repo create trading-portfolio --public --source=. --push`

### 2. Import into Vercel

1. Go to **https://vercel.com/new** and sign in with GitHub.
2. Click **Import** next to your `trading-portfolio` repo.
3. **Framework Preset:** _Other_ — leave Build & Output settings **empty**
   (it's a static site, nothing to build).
4. Click **Deploy**. ~20 seconds later you'll have a live URL like
   `https://trading-portfolio.vercel.app`.

Every `git push` to `main` now auto-deploys. 🎉

### 3. (Optional) Custom domain

In Vercel → your project → **Settings → Domains**, add a domain you own
(e.g. `israelalalibo.com`) and follow the DNS instructions.

---

## ✏️ Editing content

Everything is plain text in `index.html` — no framework to learn.

| Want to change… | Look for… |
|---|---|
| Headline / intro | `class="hero__title"` and `class="hero__lead"` |
| The headline numbers | `data-count="..."` attributes in the **stats** section |
| Your story | the **about** section |
| Milestones | the `<ol class="timeline">` list |
| Certificates shown | the `<figure class="gallery__item">` blocks |
| Contact details | the **contact** section + footer |

### Adding a new certificate later

1. Drop the image into `assets/img/` (JPG/PNG, ideally < 400 KB).
2. Copy an existing `<figure class="gallery__item">` block in `index.html`,
   update the `data-full`, `src`, `alt` and caption.
3. Commit & push — Vercel redeploys automatically.

To re-optimise raw photos/certs, re-run `python convert_assets.py`.

---

## 📝 Note on claims

All figures on the site reflect your supplied certificates ($660 in verified
payouts, 4 certified evaluation passes, 6 certificates). Keep them accurate as
your track record grows — credibility is the whole point of the page.

_Trading involves risk. Past performance does not guarantee future results._
