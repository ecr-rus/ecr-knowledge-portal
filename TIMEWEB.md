# Timeweb mirror handoff

This repository is intentionally portable. The `public` directory is a complete static artifact and can be served without a framework, database, object storage, runtime secrets, or vendor-specific content APIs.

## Proposed Timeweb deployment

1. Create a static-site application in an ECR-owned Timeweb Cloud account.
2. Select this public repository as the source.
3. Use no build command.
4. Set the publish directory to `public`.
5. Keep the generated test hostname unlinked and non-production until QA passes.
6. Confirm that the response preserves `X-Robots-Tag: noindex, nofollow`; if the platform does not import `_headers`, configure the equivalent response header in its UI.

No Timeweb account, paid resource, DNS record, or deployment is created by this handoff.

