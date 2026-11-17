# Instant Waves landing page setup

## Included

- `/en/`, `/de/` and `/fr/` entry points, with localized page copy, validation, sending states, titles, descriptions, canonicals and `hreflang`.
- Browser-language suggestion at `/`; explicit locale URLs remain stable for ads and shared links. Language changes retain form text in the current session.
- A responsive, namespaced `#iw-page` implementation. The page styles do not target other WordPress content.
- Creative and professional variants via `?variant=creative` and `?variant=professional`, with the selected version captured as `ab_version`.
- CTA and confirmed-submission data-layer events without names, email addresses or project briefs.

## Before launch

1. **Connect the endpoint.** Define `window.IW_CONFIG = { endpoint: 'https://YOUR-ENDPOINT' }` before `app.js`, or set it from the WordPress integration. The endpoint receives `multipart/form-data` and must respond with HTTP 2xx and JSON `{ "success": true }` only after durable receipt. Return any other response to show the translated error and retain the entered values. Implement server-side validation, spam protection, secure file handling, retention rules and a notification to the responsible producer. The endpoint/CRM destination and producer notification recipient are placeholders until configured.
2. **Configure WordPress routes.** Serve the matching entry point at `/en/`, `/de/`, `/fr/` (or map those paths to localized WordPress pages). Ensure the web server does not redirect these paths to the root. For a page-builder integration, add the HTML structure and load `styles.css`/`app.js`; keep the `#iw-page` wrapper intact. Set the production origin and canonical URLs in `index.html` if it differs from `https://instantwaves.com`.
3. **Replace work placeholders.** Add approved project stills or short, compressed video previews with posters, captions and accessible names. The hero uses the looping Neon Island studio video found in the supplied reference HTML, with its supplied studio still as a poster. Confirm permission to use these assets on Instant Waves pages, or substitute licensed Instant Waves footage.
4. **Review brand and contact details.** Replace the typographic IW placeholder with the approved Instant Waves logo. Confirm `service@instantwaves.com`, studio wording and the 24-hour quote promise. Add privacy notice and legal links required by the production site's jurisdiction.
5. **Wire measurement and test delivery.** Configure analytics consent behavior in the existing site. Events are `iw_cta_click` and `iw_enquiry_success`; both include language, and success also includes service and enquiry ID. Configure campaign/ad-group identifiers and keyword parameter names to match the ad platforms. The form keeps company location separate from shoot location and campaign data.
6. **Choose the A/B split.** Use the same form and endpoint for both variants. Route traffic consistently to `?variant=creative` or `?variant=professional`, and compare qualified enquiries server-side or with privacy-safe analytics. The professional variant uses a more direct brand-partner headline while the creative version keeps the ideas-in-motion positioning; both share one form and tracking setup.

The source capture supplied no usable campaign stills or showreel. The three work tiles are explicitly marked as placeholders; no client results, endorsements or performance claims are invented.

## Concept preview

The root page (`/`) is an internal chooser for review. It links to the professional direction at `/en/` (with `/de/` and `/fr/`) and the creative direction at `/creative/en/` (with `/creative/de/` and `/creative/fr/`). The creative direction uses the Instant Waves logo and promo video from the supplied page capture. Confirm asset reuse rights before publishing beyond internal review.
