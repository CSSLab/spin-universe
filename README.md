# Readout

The Readout research website: https://difanj0713.github.io/spin-universe/

This CSSLab repository contains the website source for SPIN, SIREN, MINER, and
TACIT. It was split from Difan's personal website, preserving the project's
commit history. The public website remains at the address above.

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

The public website is hosted by Difan's personal GitHub Pages repository at
`https://difanj0713.github.io/spin-universe/`. It currently keeps a separate
deployed copy. Pushing here does not automatically update that public site;
coordinate publication with Difan when changes are ready.

Keep the existing page paths and public URLs so links in papers and social
posts continue to work. A branch and pull request can be used to review edits.

Before publishing, check the changed pages on desktop and mobile, verify links
and interactive controls, and run `git diff --check`.

## License

The original repository's Apache 2.0 license is retained in [LICENSE](LICENSE).
Third-party assets retain their existing notices and attribution.
