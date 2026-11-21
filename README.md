# Portlance Exports — website

Static site for portlanceexports.com: `index.html` plus `vendor/three.min.js` (the 3D library,
bundled so the site does not depend on an outside CDN). No build step, no server code.

## Deploy on Netlify (auto-updates from GitHub)
1. app.netlify.com → **Add new project → Import an existing project → GitHub** → pick this repo.
2. Branch `main`. Leave base directory, build command and publish directory empty
   (`netlify.toml` already says: no build, publish this folder). Deploy.
3. **Domain management → Add a domain** → `portlanceexports.com`, then add the DNS records
   Netlify shows in GoDaddy (My Products → domain → DNS). Remove any GoDaddy forwarding/parking.

Every push to `main` redeploys the site automatically.

## Enquiry emails (Netlify Forms)
1. Netlify → **Forms** → **Enable form detection** (if shown), then trigger a redeploy.
2. **Forms → Form notifications → Add notification → Email notification** → form `quote`,
   address `mishalms596@gmail.com`.
Free plan: 100 submissions/month; every submission is also listed under Forms.
A hidden honeypot field filters basic spam bots. On hosts without Netlify Forms the form falls back
to opening the visitor's email app.

## Editing
Company details, product spec and contact email are plain text in `index.html`
(search for `Portlance`, `7–8 mm`, `mishalms596`). Add a phone / WhatsApp number and address
to the contact section if you want them shown.

## Preview locally
`python3 -m http.server 8000` in this folder, then open http://localhost:8000
