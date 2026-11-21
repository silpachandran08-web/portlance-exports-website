# Portlance Exports — website

Static site for portlanceexports.com: `index.html` plus `vendor/three.min.js` (the 3D library,
bundled so the site does not depend on an outside CDN). No build step, no server code.

## Hosting
Deployed on Vercel from this repo's `main` branch: every push to `main` redeploys automatically.
No build step: Vercel serves `index.html` and `vendor/` as static files.

## Enquiry emails (FormSubmit)
The quote form posts to formsubmit.co, which emails each enquiry to the address in the form's
`data-email` attribute (`mishalms596@gmail.com`). No account or server code is needed.
- **One-time activation:** the very first enquiry makes FormSubmit send an "Activate Form" email to
  that inbox. Click the link in it once; every enquiry after that is delivered.
- Replying to an enquiry email replies to the buyer (their address is set as reply-to).
- A hidden honeypot field filters basic spam bots.
- If FormSubmit can't be reached (or isn't activated yet), the form opens the visitor's email app
  with the enquiry filled in instead.

## Editing
Company details, product spec and contact email are plain text in `index.html`
(search for `Portlance`, `7–8 mm`, `mishalms596`). Add a phone / WhatsApp number and address
to the contact section if you want them shown.

## Preview locally
`python3 -m http.server 8000` in this folder, then open http://localhost:8000
