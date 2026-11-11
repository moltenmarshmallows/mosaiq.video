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

The current apex content and infrastructure were not accessible while preparing
this repository. The landing page is a placeholder and must be wired up in
`mosaiq-infra` before it is published.
