# denrzv.github.io

This origin serves the **Bloom Flowers** reference integration for the
[SiteSkin](https://github.com/denrzv/webora) protocol — a browser-agnostic format that lets a
website describe its own navigation and branding.

- The site itself: <https://github.com/denrzv/bloom-flowers>
- How to integrate your own site: [`INTEGRATION.md`](https://github.com/denrzv/bloom-flowers/blob/main/INTEGRATION.md)

## Why the site lives here and not in this repository

SiteSkin discovery requests `/.well-known/siteskin.json` at the **origin root**, and the reference
manifest's paths (`/catalog`, `/cart`, `/account`) are origin-absolute. A GitHub Pages *project*
site is served from a subpath, where that well-known path belongs to whoever owns the user-site root
and every manifest path resolves outside the deployment — so a project page cannot host a SiteSkin
integration at all. A user site owns its root, which is why the demo is served from here.

Nothing is copied. [`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) checks out
`denrzv/bloom-flowers` at deploy time and publishes it, so the manifest keeps one source of truth
and its SHA-256 — pinned in both `denrzv/bloom-flowers` and `denrzv/webora` — remains the only thing
that has to agree.

This is a **verification stopgap**. The permanent home is `bloomflowers.webora.app`, pending a DNS
record, and the wider demo fleet needs four distinct origins that a single Pages root cannot supply.

## What used to be here

A 2018 practice project, *Colmar Academy*. It is not deleted — it is preserved unchanged on the
[`archive/colmar-academy`](https://github.com/denrzv/denrzv.github.io/tree/archive/colmar-academy)
branch, and restoring it is one `git push` of that branch back onto `master`.
