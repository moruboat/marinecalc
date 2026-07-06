# MarineCalc prototype

Static single-file prototype for a marine engineering calculator site
(tonnage, paint, composites, pipe specs, propeller pitch, weights,
anchor equipment number, and a vessel-particulars input hub).

No build step, no server, no dependencies. Pure HTML/CSS/JS.

## Deploy with GitHub Pages

1. Create a new GitHub repository (e.g. `marinecalc`).
2. Upload `index.html` (and this `README.md`) to the repository root.
3. Go to Settings -> Pages.
4. Under "Build and deployment", set Branch to `main` and folder to `/ (root)`.
5. Save. After a minute or two, the site is live at:
   `https://<your-github-username>.github.io/marinecalc/`

## Connect a custom domain (e.g. marinecalc.com)

1. Add a file named `CNAME` (no extension) to the repository root containing
   just the domain name: `marinecalc.com`
2. At your domain registrar, point the domain's DNS to GitHub Pages
   (A records to GitHub's IPs, or a CNAME record if using a subdomain).
3. Back in Settings -> Pages, enter the custom domain and enable
   "Enforce HTTPS" once GitHub finishes provisioning the certificate.

## What's real vs. mocked in this prototype

- All 12 calculators: fully functional, client-side only.
- Language toggle (KO/EN/JA) and unit toggle (Metric/Imperial): fully functional.
- Vessel particulars hub, manual entry tab: fully functional, pushes values
  into the calculators below.
- Vessel particulars hub, drawing upload tab: **mocked**. Dropping any file
  shows a fixed demo result labeled "DEMO" - there is no real image/PDF
  analysis wired up. Implementing real analysis requires a server-side
  component (see note below).
- Search box: functional client-side filter over calculator names.
- Ad slots: placeholder blocks only, no ad network integrated yet.

## Next step for real drawing analysis

The upload tab needs a backend call (Cloudflare Pages Functions or similar)
to an OCR/vision API (e.g. Google Cloud Vision) to actually read a drawing.
That piece is not included here since it requires server-side deployment
and API credentials.
