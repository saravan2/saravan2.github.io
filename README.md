# Personal Website

Source for my personal website, built with [Zola](https://www.getzola.org/) (a fast, single-binary static site generator written in Rust).

## Structure

```
config.toml          Site configuration + sidebar/nav data ([extra])
content/             Markdown content
  _index.md            Home page
  oss-contributions.md
  terms.md
  publications/        Publications section (one .md per paper)
templates/           Tera templates (base, page, publications, sidebar macro)
sass/main.scss       Hand-rolled minimal styles
static/              Static assets (images, resume PDF) served at site root
```

## Running locally

1. Install Zola: https://www.getzola.org/documentation/getting-started/installation/
2. `zola serve` — builds and serves at http://127.0.0.1:1111 with live reload.
3. `zola build` — outputs the static site to `./public`.

## Deployment

Two GitHub Actions deploy `master` to two hosts from the same source:

1. **`build-deploy-s3.yml`** → builds with Zola and `aws s3 sync`s to the S3 bucket behind **https://saravanand.com**.
2. **`deploy-gh-pages.yml`** → builds (with base-url override) and publishes to GitHub Pages at **https://saravan2.github.io** via the artifact/`deploy-pages` mechanism.

> GitHub Pages source must be set to **"GitHub Actions"** in repo Settings → Pages for the second workflow to publish.

## Adding a publication

Drop a new markdown file in `content/publications/` with front matter (`title`, `date`, and `[extra]` fields like `venue`, `paperurl`, `citation`). It appears automatically in the publications list, sorted newest-first.
