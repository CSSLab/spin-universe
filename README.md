# Readout

CSSLab website and preview: https://csslab.github.io/spin-universe/

This CSSLab repository contains the website source for SPIN, SIREN, MINER, and
TACIT. It was split from Difan's personal website, preserving the project's
commit history. Difan's existing website at
https://difanj0713.github.io/spin-universe/ is a separate deployment and is
not changed by commits or deployments in this repository.

## Editing

The site uses plain HTML, CSS, and JavaScript. There is no build step.

- `index.html`: Readout homepage
- `spin/`, `siren/`, `miner/`, `tacit/`: generated full-text paper pages
- `team/`: collaborators
- `assets/`: styles, scripts, figures, and other shared assets
- `agent-siren/`: redirect from the former TACIT URL

See [BRANDING.md](BRANDING.md) for the site's voice and visual style. The full-text
paper pages now use the importer below; the landing-page layouts in
[EDITORIAL_GUIDE.md](EDITORIAL_GUIDE.md) describe the earlier version.

## Import full papers

The four paper URLs contain the complete arXiv HTML articles, including figures,
MathML equations, footnotes, references and appendices. The importer does not
summarize or rewrite the papers. It downloads the figures locally and applies
one shared reading layout inspired by Anthropic's research articles.

```sh
python3 -m pip install -r scripts/requirements.txt
python3 scripts/import_arxiv.py
# Or regenerate just one paper:
python3 scripts/import_arxiv.py tacit
```

Versions and publication dates are pinned in `scripts/papers.json`. To update a
paper, change its version/date there and run the importer. Downloads are cached
in `.cache/arxiv/`; `--refresh` downloads them again. Commit the generated HTML
and assets so GitHub Pages needs no build dependencies. Asset provenance and
source hashes are recorded in `assets/papers/<slug>/source.json`.

Edit `assets/css/paper.css` and `assets/js/paper.js` for shared presentation and
footnote behavior. Edit `scripts/import_arxiv.py` for structural changes. The
generated `index.html` files are overwritten by the importer. A future editorial
version can be built from these full texts after review.

## Preview locally

Clone the repository into a directory named `spin-universe`, then run:

```sh
cd spin-universe
python3 -m http.server 8080 --bind 127.0.0.1 --directory ..
```

Open http://localhost:8080/spin-universe/. Serving from the parent directory
preserves the `/spin-universe/` paths used on the live site.

## Publishing

Pushing to `main` deploys this repository through GitHub Pages to
`https://csslab.github.io/spin-universe/`. Ashton can review and edit this version.
Difan's personal GitHub Pages repository keeps its own deployed copy; pushing
here does not update `https://difanj0713.github.io/spin-universe/`.

Keep the existing page paths and public URLs so links in papers and social
posts continue to work. A branch and pull request can be used to review edits.

Before publishing, check the changed pages on desktop and mobile, verify links
and interactive controls, and run `git diff --check`.

## License

The original repository's Apache 2.0 license is retained in [LICENSE](LICENSE).
Third-party assets retain their existing notices and attribution.
