# ECR Knowledge Portal - safe preview

Portable, static review build for the ECR meeting dated 19 August 2026.

## Release identity

- Approved source version: `0d8fe16`
- Rollback source: `76c1663`
- Approved package SHA-256: `247231ce37579998314f66562607f6bec6f9712a075c968eb48009eb585c64c1`
- Cloudflare Pages project: `ecr-knowledge-portal`
- Deployment mode: manual `workflow_dispatch` only
- Indexing policy: `noindex, nofollow` in HTML and response headers

## Repository layout

- `public/index.html` - rights-safe public-review page
- `public/_headers` - crawler and content-type protections
- `.github/workflows/deploy-preview.yml` - manual deployment to the existing Pages project
- `TIMEWEB.md` - portable mirror instructions

## Required GitHub Actions secrets

The values are stored directly in GitHub repository settings and are never committed:

- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`

The workflow does not create Cloudflare projects, DNS records, storage services, databases, queues, repositories, or runtime secrets.

## Local verification

Serve the `public` directory with any static HTTP server, inspect the rendered page, and confirm both the HTML robots meta tag and `_headers` policy before a manual deployment.

