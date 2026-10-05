# Readout

The Readout research website: https://csslab.github.io/spin-universe/

This repository contains the website for SPIN, SIREN, MINER, and TACIT. It was
split from Difan's personal website, preserving the project's commit history.

## Editing

The site uses plain HTML, CSS, and JavaScript. There is no build step.

- `index.html`: Readout homepage
- `spin/`, `siren/`, `miner/`, `tacit/`: paper pages
- `team/`: collaborators
- `assets/`: styles, scripts, figures, and other shared assets
- `agent-siren/`: redirect from the former TACIT URL

See [BRANDING.md](BRANDING.md) for the site's voice and visual style, and
[EDITORIAL_GUIDE.md](EDITORIAL_GUIDE.md) for the paper-page conventions.

## Preview locally

Clone the repository into a directory named `spin-universe`, then run:

```sh
cd spin-universe
python3 -m http.server 8080 --bind 127.0.0.1 --directory ..
```

Open http://localhost:8080/spin-universe/. Serving from the parent directory
preserves the `/spin-universe/` paths used on the live site.

## Publishing

GitHub Pages publishes the root of `main`. Pushing to `main` updates the live
site; a branch and pull request can be used to review changes first.

The site is maintained in [CSSLab/spin-universe](https://github.com/CSSLab/spin-universe).
Keep the existing repository name and page paths when editing.

The former website at `https://difanj0713.github.io/spin-universe/` redirects to
this site. Those redirects and legacy assets live in Difan's personal website
repository so previously shared links continue to work.

Before publishing, check the changed pages on desktop and mobile, verify links
and interactive controls, and run `git diff --check`.

## License

The original repository's Apache 2.0 license is retained in [LICENSE](LICENSE).
Third-party assets retain their existing notices and attribution.
