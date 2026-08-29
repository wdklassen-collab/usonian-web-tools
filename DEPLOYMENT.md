# Usonian Guitar Co. Production Deployment

This file is the canonical deployment reference for the Usonian Guitar Co. website.

## Canonical production map

| Role | Canonical value |
|---|---|
| GitHub repository | `wdklassen-collab/usonian-web-tools` |
| Production branch | `main` |
| Cloudflare Worker | `usonian-guitar-company` |
| Primary domain | `usonianguitar.com` |
| WWW domain | `www.usonianguitar.com` |

## Naming rule

`usonian-web-tools` is only the GitHub repository name.

Do **not** create, deploy to, bind a domain to, or otherwise use a Cloudflare Worker named `usonian-web-tools` for production.

The only production Worker is:

`usonian-guitar-company`

## Expected deployment flow

1. Edit files in `wdklassen-collab/usonian-web-tools`.
2. Commit changes to `main`.
3. Cloudflare builds/deploys that commit to `usonian-guitar-company`.
4. `usonianguitar.com` and `www.usonianguitar.com` serve that Worker.

## Production verification

After every website change, verify all three of the following before calling the change deployed:

- The expected commit exists on `main`.
- Cloudflare shows a deployment newer than that commit/change.
- The public domain visibly serves the changed content.

A GitHub commit by itself is **not** a production deployment.

## Cloudflare domain bindings

The production Worker should have these domains only:

- its Cloudflare-provided `workers.dev` hostname
- `usonianguitar.com`
- `www.usonianguitar.com`

If another Usonian Worker or Pages project has either custom domain attached, treat that as a configuration error and remove the duplicate binding after confirming the production Worker above is healthy.

## Troubleshooting

If GitHub changed but the website did not:

1. Check the latest commit on `main`.
2. Check Cloudflare → `usonian-guitar-company` → Deployments.
3. If there is no deployment corresponding to the new commit, the GitHub-to-Cloudflare build trigger is not running.
4. Do not create a second Worker as a workaround.
5. Repair the source/build connection so `main` deploys to `usonian-guitar-company`.

## Historical note

Older documentation referred to GitHub Pages. GitHub Pages is not the canonical production target for UsonianGuitar.com.
