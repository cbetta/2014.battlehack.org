# BattleHack 2014

A static archive of the 2014 BattleHack site, served at
[battlehack2014.betta.io](https://battlehack2014.betta.io). It was
2014.battlehack.betta.io until October 2026, when betta.io moved to Cloudflare,
whose free certificate only covers one level below betta.io.

## Hosting

The site is the plain files at the root of this repo, served by nginx on
jiji, Cristiano's home server, behind its Cloudflare tunnel. `nginx.conf`
keeps Netlify's URL rules: `/london` and `/london/` both serve
`london/index.html`.

A push to `master` runs `.github/workflows/publish.yml`: CI, then the image
`ghcr.io/betta-apps/2014.battlehack.org`, which it pins in jiji's `docker-compose.yml` to
deploy. `scripts/check.sh` checks every local link resolves;
`scripts/smoke.sh` builds the image and boots it.
