# Enabling GitHub Pages for this repository

The Jekyll site content and the deploy workflow (`.github/workflows/jekyll.yml`) are in
place. The workflow currently fails at the "Configure GitHub Pages" step with
`Resource not accessible by integration`, because the workflow's `GITHUB_TOKEN` cannot
create the Pages site under the repository's current permission settings (common for
forked repositories).

This is a one-time owner action in repository **Settings** — no files need to change:

1. **Settings → Actions → General → Workflow permissions** → choose **"Read and write"**.
2. **Settings → Pages → Build and deployment** → set **Source** to **"GitHub Actions"**.

Then re-run the workflow (or push any change to `master`).
`Deploy Academic Pages template site to Pages` will succeed and publish the site at:

<https://pentagonjellyfish.github.io/LJT-Homepage/>

The workflow already uses `actions/configure-pages@v6.0.0` with `enablement: true`
and `actions/deploy-pages`, so once the settings above are applied it works without
any further edits.
