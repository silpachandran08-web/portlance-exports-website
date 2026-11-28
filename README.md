# Portlance Exports — website

Static site for portlanceexports.com (black pepper and green cardamom): `index.html` plus
`vendor/three.min.js` (the 3D library, bundled so the site does not depend on an outside CDN).
No build step, no server code.

## How the page works
- **Hero:** a true-scale, slow-motion rain of whole black peppercorns and 7-8 mm green cardamom pods
  falling onto a glass floor (reflections, contact shadows). Each piece bounces a few times, slides and
  settles. Every few seconds a random falling piece is drawn toward the lens for a close-up and returns.
- **Export (next page):** sacks are lowered into a see-through container, the doors close, then the
  sealed container in the port yard.
- **Spec bench:** both specimens at true relative size on a millimetre ruler (drag to turn), with
  "Add to enquiry" buttons that pre-fill the form.
- **Performance:** only the visible zone is drawn; drawing stops while the 3D is covered; phones /
  low-memory devices get a lighter tier; quality steps down automatically if frames are slow.

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
(search for `Portlance`, `7–8 mm`, `Black pepper`, `mishalms596`). Add a phone / WhatsApp number and address
to the contact section if you want them shown.

## Preview locally
`python3 -m http.server 8000` in this folder, then open http://localhost:8000
