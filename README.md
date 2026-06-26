# SASE controls map — sase.cyberassure.uk

Interactive, animated Secure Access Service Edge reference architecture showing how
**ZTNA**, **Defence in Depth** and **PAM** requirements are fulfilled. Vendor-neutral,
single static page, no build step, no runtime dependencies (web fonts aside).

## Contents
- `index.html` — the entire site (inline CSS + SVG + JS)
- `vercel.json` — clean URLs and security response headers (CSP, HSTS, etc.)

## Deploy (GitHub → Vercel)
1. Create a new GitHub repo and push this folder (see commands below).
2. In Vercel: **Add New → Project → Import** the repo. Framework preset: **Other**.
   Build command: *none*. Output directory: *root*. Deploy.
3. **Project → Settings → Domains → Add** `sase.cyberassure.uk`.
4. At the DNS host for `cyberassure.uk`, add the record Vercel shows — normally:
   `CNAME  sase  →  cname.vercel-dns.com`
5. Wait for DNS to verify; Vercel issues the TLS certificate automatically.

## Push commands
```bash
git init -b main
git add .
git commit -m "SASE controls map"
git remote add origin git@github.com:<you>/<repo>.git
git push -u origin main
```

## Notes
- The page uses inline `<style>` and `<script>`, so the CSP allows `'unsafe-inline'`.
  To remove that, split CSS/JS into `styles.css` / `app.js` and tighten the policy.
- Respects `prefers-reduced-motion`; responsive down to mobile.
