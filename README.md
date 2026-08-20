# Isola — static site

| File | What it is |
| --- | --- |
| `index.html` | Landing page |
| `demo.html` | The worked example, runs entirely in the browser |
| `terms.html` | Terms of service |
| `privacy.html` | Privacy policy |
| `404.html` | Not-found page |
| `style.css` | Shared styling for everything except the demo |
| `_headers` | Security headers, read by Cloudflare Pages |

The landing page and the demo. Both are plain HTML with no build step and
no server, so they host free anywhere.

The demo runs entirely in the browser against a worked example. Nothing is
sent anywhere and there is nothing to sign up for.

## Deploying free

**Cloudflare Pages** — what this is deployed on.

1. Push to GitHub
2. Cloudflare dashboard → Workers & Pages → Create → Pages → connect the repo
3. Build command: leave empty. Build output directory: `site`

Every push to `main` redeploys automatically. `_redirects` and `_headers`
are read by Pages directly; there is no build step to configure.

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

## A note on extensions

Cloudflare Pages serves `demo.html` at `/demo` on its own and 308-redirects
the `.html` form to the extensionless one. A `_redirects` rule rewriting
`/demo` back to `/demo.html` therefore created an infinite loop.

Link to `/demo`, `/terms` and `/privacy` without extensions. There is no
redirect rule and none is needed.
