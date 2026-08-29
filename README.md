# Usonian Guitar Co. Website & Web Tools

This repository is the source code for **UsonianGuitar.com** and its browser-based lutherie tools.

## Production architecture

- **Source repository:** `wdklassen-collab/usonian-web-tools`
- **Production branch:** `main`
- **Cloudflare Worker:** `usonian-guitar-company`
- **Production domains:** `https://usonianguitar.com` and `https://www.usonianguitar.com`

> `usonian-web-tools` is the repository name. It is **not** a production Worker name and should never be used as a Cloudflare deployment target.

## Website and tools

- Home: `/`
- Products & Services: `/products-services/`
- Fretboard Generator: `/fretboard/`
- Radius Dish Creator: `/radiusdishcreator/`
- Neck Template Generator: `/neck-template/`
- Nut Spacing Guide: `/nut-spacing/`

All browser tools run client-side; no user account is required.

## Deployment rule

Every production deployment must target the Cloudflare Worker **`usonian-guitar-company`**. Do not create or deploy to a Worker named `usonian-web-tools`.

See [`DEPLOYMENT.md`](DEPLOYMENT.md) for the canonical deployment map and troubleshooting checklist.
