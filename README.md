# Readout

Live site: https://csslab.github.io/spin-universe/

Website source for SPIN, SIREN, MINER and TACIT. Plain HTML, CSS and
JavaScript, no build step. Split from Difan's personal site, whose deployment
at https://difanj0713.github.io/spin-universe/ is separate and unaffected by
this repository.

## Layout

- `index.html`: homepage
- `spin/`, `siren/`, `miner/`, `tacit/`: one research article per paper
- `team/`: collaborators
- `assets/`: styles, scripts and figures
- `agent-siren/`: redirect from the former TACIT URL

Edit a paper page by editing its `index.html`. The shared article layout is
`assets/css/research-article.css`. Voice and visual style are in
[BRANDING.md](BRANDING.md).

## Importer

`scripts/import_arxiv.py` can regenerate a paper page as the full arXiv HTML
article. All four entries in `scripts/papers.json` are marked
`"presentation": "editorial"`, which the importer skips, so running it leaves
the edited articles alone. To regenerate a page, remove that flag first; the
edited article is overwritten.

```sh
python3 -m pip install -r scripts/requirements.txt
python3 scripts/import_arxiv.py tacit
```

## Preview

Clone into a directory named `spin-universe`, then:

```sh
cd spin-universe
python3 -m http.server 8080 --bind 127.0.0.1 --directory ..
```

Open http://localhost:8080/spin-universe/. Serving from the parent directory
keeps the `/spin-universe/` paths used on the live site.

## Publishing

Pushing to `main` deploys through GitHub Pages. Keep existing page paths so
links in papers and posts keep working. Check changed pages on desktop and
mobile before pushing.

## License

Apache 2.0, see [LICENSE](LICENSE). Third-party assets keep their own notices.
