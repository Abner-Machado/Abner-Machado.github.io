# abner-machado.github.io

My personal site. Static, built with [Hugo](https://github.com/gohugoio/hugo), deployed
to GitHub Pages by Actions on every push to `main`.

Live at https://abner-machado.github.io

## Why it is built this way

- No npm. Hugo is a single binary, so there is no `node_modules` and nothing to
  audit on install.
- No CDN. Fonts are self-hosted from `static/fonts/`, trimmed to the latin and
  latin-ext subsets. Nothing on the page calls a third-party domain, so no visitor of
  this site is logged by anyone but GitHub.
- No trackers. There is no analytics script.
- No theme. Layouts and CSS are written for this site.

## Run it locally

```bash
hugo server
# http://localhost:1313
```

Build what CI builds:

```bash
hugo --gc --minify
```

## Layout

```
content/          Markdown. One file per post in content/posts/.
layouts/          Templates. baseof, home, section, page, plus _partials/.
assets/css/       Stylesheet, bundled and fingerprinted by Hugo.
static/fonts/     Self-hosted woff2 and the @font-face rules.
.github/workflows Build, sanity-check the output, deploy.
```

## New post

```bash
hugo new content posts/the-slug.md
```

Front matter that matters: `title`, `date`, and `description`. The description is what
shows in the list and in link previews; without it Hugo falls back to the first lines of
the body.

## License

Code and templates: [MIT](LICENSE). Post text is mine, all rights reserved.

Fonts are third party and keep their own terms: Inter, Playfair Display and JetBrains
Mono are all under the SIL Open Font License 1.1.
