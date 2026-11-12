# pramana-research.com

Static landing page for Pramana Research. No build step: `index.html` is the whole site
(HTML, CSS and the scroll animation in one file). `vercel.json` adds clean URLs and basic
security headers.

## Preview locally

```bash
cd pramana-site
python3 -m http.server 8080      # then open http://localhost:8080
```

## Deploy to Vercel

**Option A: from GitHub (recommended: every push redeploys)**

```bash
cd pramana-site
git init && git add -A && git commit -m "Pramana Research landing page"
gh repo create pramana-site --private --source=. --push
```

Then on vercel.com: **Add New → Project → Import** `pramana-site` →
Framework preset **Other**, leave Build Command and Output Directory empty → **Deploy**.

**Option B: from the command line**

```bash
npm i -g vercel
cd pramana-site
vercel          # first run: log in, accept the defaults
vercel --prod
```

## Connect pramana-research.com

1. Vercel → your project → **Settings → Domains** → add `pramana-research.com`
   and `www.pramana-research.com`.
2. Vercel shows the DNS records to create. At your domain registrar, add them, typically:
   - `A` record, host `@`, pointing to the IP address Vercel shows
   - `CNAME` record, host `www`, pointing to the target Vercel shows
3. Wait for DNS to propagate (minutes to a few hours). Vercel issues the HTTPS
   certificate automatically.

Use the exact values Vercel displays for your project; they can differ from the examples.

## Before sharing the link

- Create the mailbox `hello@pramana-research.com`: both "Request early access" buttons
  and the contact button send email there.
- Editing copy: change the text directly in `index.html` and push (or run `vercel --prod`).
