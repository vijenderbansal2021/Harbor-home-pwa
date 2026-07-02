# Harbor Home — Florida Home Insurance PWA (Prototype)

A single-file installable Progressive Web App demonstrating the **quote-to-bind**
flow from the Personal Home Insurance PRD:
**Login → Register → Submission → Quote → Bind → Pay → Issue → Declarations.**

This is a **business-demo prototype**. All external integrations are *simulated*:
- **Verisk** property pre-fill → hardcoded property attributes shown as chips
- **USPS** address validation → mocked "validated" state
- **JPMC / PayPal** payments → mocked, no real charge, no card data stored
- **Rating engine** → a client-side premium formula (illustrative, not filed rates)

## Run locally
Just open `index.html` in a browser, or serve it:
```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Deploy to GitHub Pages
1. Create a new repository (e.g. `harbor-home-pwa`) and push these files:
   ```bash
   git init
   git add .
   git commit -m "Harbor Home insurance PWA prototype"
   git branch -M main
   git remote add origin https://github.com/<you>/harbor-home-pwa.git
   git push -u origin main
   ```
2. In the repo: **Settings → Pages → Build and deployment**
   - Source: *Deploy from a branch*
   - Branch: `main` / root (`/`)
3. Wait ~1 minute. Your app is live at
   `https://<you>.github.io/harbor-home-pwa/`
4. On mobile, open that URL and choose **Add to Home Screen** to install it as an app.

The `.nojekyll` file is included so GitHub Pages serves all files as-is.

## What to show business
- Tap **Face ID** on the login screen for the returning-user path (0 inputs).
- On the Quote screen, drag the **sliders** — premium recalculates live.
- Raise the **hurricane deductible** to show the premium credit.
- Complete **Bind → Pay** to see the auto-generated **Declarations page** and
  the "bound in X seconds" timer that proves the under-10-minute promise.

## Not included (would require the real backend + carrier contracts)
Live rating, real underwriting rules, actual payment settlement, filed FL
statutory forms, e-signature audit trail, policy-admin persistence.
