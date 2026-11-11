# mosaiq.video

The static landing page for the `mosaiq.video` apex. `index.html` is the
deployable site; it has no build step, dependencies, or runtime configuration.

Preview locally from the repository root:

```sh
python3 -m http.server 8000
```

Open <http://localhost:8000/>. Publish `index.html` at the origin root as
`index.html` with `Content-Type: text/html; charset=utf-8`; requests to `/`
must serve it. Do not publish the repository's `.git` directory or other
repository metadata.

## Handoff prompt for mosaiq-infra

> Inspect the existing Terraform and deployment setup for `mosaiq.video` before
> making changes. Replace the existing apex landing-page content source with the
> static `index.html` from `moltenmarshmallows/mosaiq.video`, using the
> repository's `main` branch as the production source. Set up an automated,
> least-privilege deployment on changes to that branch using the existing
> hosting provider and CI conventions; publish the file at the origin root
> with the HTML content type and make `/` serve it. No build command or
> environment variables are required.
>
> Keep Terraform authoritative for infrastructure and avoid managing the same
> website content from both Terraform and the deployment pipeline. Preserve
> existing DNS, TLS, redirects, and any non-landing-page routes and services;
> inspect their actual configuration rather than assuming a provider or
> replacing the whole zone. Configure any needed cache invalidation so updates
> appear at the apex. Document required repository permissions/secrets without
> committing credentials, deployment and rollback steps, and any bootstrap
> ordering. Review the Terraform plan for unintended changes, then verify HTTPS
> `https://mosaiq.video/` serves the new page and existing routes still work.
> Retain a way to restore the previous page if deployment fails.

The current apex content and infrastructure were not accessible while preparing
this repository. The landing page is a placeholder, and the handoff must be
completed in `mosaiq-infra` before it is published.
