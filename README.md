# Isola — static site

| File | What it is |
| --- | --- |
| `index.html` | Landing page |
| `demo.html` | The worked example, runs entirely in the browser |
| `terms.html` | Terms of service |
| `privacy.html` | Privacy policy |
| `404.html` | Not-found page |
| `style.css` | Shared styling for everything except the demo |

The landing page and the demo. Both are plain HTML with no build step and
no server, so they host free anywhere.

The demo runs entirely in the browser against a worked example. Nothing is
sent anywhere and there is nothing to sign up for.

## Deploying free

**Cloudflare Pages** — best of the three. Unmetered bandwidth, fast
everywhere, free custom domain and certificate.

1. Push this folder to GitHub
2. Cloudflare dashboard → Workers & Pages → Create → Pages → connect the repo
3. Build command: leave empty. Output directory: `site`

**Netlify** — drag this folder onto app.netlify.com/drop. Live in seconds,
no account needed to try it.

**GitHub Pages** — Settings → Pages → deploy from branch, folder `/site`.
Free custom domain, but no server-side redirects.

## Custom domain

All three: add the domain in their dashboard, then point a CNAME at the
host they give you. Certificates issue automatically.

## What is not here

The application itself. It needs a persistent database, which static
hosts cannot provide — see `../DEPLOY.md`.

When the app goes live, change the two call-to-action links in
`index.html` from the mailto back to `/app`.

## Before you take money

Section 6 of the privacy policy sets out a real conflict — the ledger is
append-only, and the right to erasure says people can ask to be deleted.
The position taken is that account details are deleted while ledger
entries are anonymised and retained for six years. That reasoning is worth
a solicitor's view before you have paying customers.

Both pages carry a "last updated" date. Change it when you change them.
