# wheez-landing

The wheez.civai.co marketing site. Static HTML — no build step, no backend.

## What this is

`index.html` is the marketing-site design prototype (customer hero, how-it-works, vs-comparison,
vendor pitch, rider pitch, FAQ, plus the vendor/rider onboarding wizards) exported as-is from the
`wheez` monorepo's `design/` folder. It's self-contained: `support.js` loads React, ReactDOM and
Babel from CDN at runtime and renders the templated markup in `index.html` — there's nothing to
build or compile.

The vendor/rider "Apply" wizards and their bank-account/CAC/OTP checks are **visual demos only** —
they simulate validation with timers, not real checks, and submissions go nowhere. They're kept
in for design fidelity with the prototype, not as working signup flows.

## Deploy

Push to `main` → [`.github/workflows/pages.yml`](.github/workflows/pages.yml) publishes the repo
root straight to GitHub Pages (`actions/upload-pages-artifact` + `actions/deploy-pages`, no build
step). Repo Settings → Pages → Source is set to **GitHub Actions**.

`CNAME` pins the custom domain to `wheez.civai.co`. That only resolves once civai.co's DNS has a
CNAME record for `wheez` pointing at `civai-technologies.github.io` — that's a Cloudflare change
outside this repo.

## Mirror & deploy

Same convention as the other wheez-* repos: `civai-technologies/wheez-landing` is the repo of
record, mirrored to `mrkeyiano/wheez-landing` for dev access. No feature branches — push straight
to `main`.
