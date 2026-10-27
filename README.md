# raeslab.org redirects

This repository keeps the old `raeslab.org` URLs (as printed in papers) working by
redirecting them to their new locations. It is a small Jekyll site hosted on
GitHub Pages and uses the [`jekyll-redirect-from`](https://github.com/jekyll/jekyll-redirect-from)
plugin, which GitHub Pages supports out of the box.

| From                                  | To                                  |
|---------------------------------------|-------------------------------------|
| `https://raeslab.org/`                | `https://raeslab.sites.vib.be/`     |
| the old companion and software URLs   | see [Redirects in place](#redirects-in-place) |
| any other (unknown) path              | 404 page linking to the lab site    |

## Redirects in place

Every old URL below was confirmed against the Internet Archive (so the paths are
the ones that really existed, not guesses), and every target was checked to
return HTTP 200. `W1–W13` style ranges mean one redirect file per number.

All old paths are relative to `https://raeslab.org`; the `www.raeslab.org` forms
printed in most papers are 301'd to the apex domain by GitHub Pages, keeping the
path, so they land on the same redirects. Alternate spellings listed under
`redirect_from` take two hops (alias → canonical path → target); the canonical
path takes one. Both the `ocean_interactome`
(underscore, the real old folder) and `ocean-interactome` (hyphen, as printed in
the Science references) spellings are covered, as are the malformed variants that
appear in print.

### Companion sites

| Old URL | New target |
|---|---|
| `/companion/ocean-interactome.html`<br>`/companion/ocean_interactome/` | [Tara-Oceans-Plankton-Interactome](https://github.com/raeslab/Tara-Oceans-Plankton-Interactome) |
| `/companion/ocean-carbon-export.html`<br>`/companion/ocean_carbon_export/` | [Tara-Oceans-Plankton-Networks](https://github.com/raeslab/Tara-Oceans-Plankton-Networks) |
| `/companion/vlaams-darmflora-project.html`<br>`/companion/vlaams_darmflora_project/` | <https://code.raeslab.org/FGFP-Gut-Microbiome-Variation/> |
| `/companion/fgfp-gwas/` | <https://code.raeslab.org/fgfp-gwas/> |
| `/companion/stool-consistency.html`<br>`/companion/stool_consistency/` | <https://code.raeslab.org/Stool-Consistency-Gut-Microbiota/> |
| `/companion/suppdata/`<br>`/companion/suppdata/index.html`<br>`/companion/suppdata/downloads.html` | <https://code.raeslab.org/Small-Intestinal-Microbiota/> |
| `/companion/gmms/` | <https://code.raeslab.org/GMMs/> |

### Tara Oceans deep links

These are the individual files cited in Lima-Mendez *et al.* (Science 2015) and
Guidi *et al.* (Nature 2016). They point at GitHub raw URLs, which is where the
migrated repositories actually serve their data from.

| Old URL | New target |
|---|---|
| `/companion/ocean_interactome/tables/W1.xlsx` – `W13.xlsx` | `…/Tara-Oceans-Plankton-Interactome/raw/main/docs/data/tables/W<n>.xlsx` |
| `/companion/ocean_interactome/tablesW1.xlsx` – `tablesW13.xlsx`<br>(missing slash, as printed) | same as above |
| `/companion/ocean_interactome/figures/W1.pdf` – `W9.pdf` | `…/raw/main/docs/data/figures/W<n>.pdf` |
| `/companion/ocean_interactome/companion_figures/W1.pdf` – `W9.pdf` | same as above |
| `/companion/ocean_interactome/figures/W9.fas` | `…/raw/main/docs/data/figures/W9.fas` |
| `/companion/ocean_interactome/Accompanying_Material.docx` | `…/raw/main/docs/data/Accompanying_Material.docx` |
| `/companion/ocean_carbon_export/tables/SI.tables.xlsx` | `…/Tara-Oceans-Plankton-Networks/raw/main/docs/data/tables/SI.tables.xlsx` |
| `/companion/ocean_carbon_export/tables/norm.abundance.matrices.zip` | `…/raw/main/docs/data/tables/norm.abundance.matrices.zip` |

The double-slash forms printed in the references (`figures//W1.pdf`,
`/companion//ocean_interactome/…`) need no redirect files of their own: GitHub
Pages collapses duplicate slashes before matching, which was verified against the
live site.

### Software pages

| Old URL | New target |
|---|---|
| `/software/BMIS/` | <https://code.raeslab.org/BMIS/> |
| `/software/QMP2/` | <https://code.raeslab.org/QMP-PSC-IBD/> |
| `/software/QMP2/QMP.matrix.tsv` | `…/QMP-PSC-IBD/raw/main/supplementary/QMP.matrix.tsv` |
| `/software/BMT/`<br>`/software/BMT/index.html` | [benchmark_microbiome_transformations](https://github.com/raeslab/benchmark_microbiome_transformations) |
| `/software/QMP_temporal/`<br>`/software/QMP_temporal/index.html` | [temporal_variability_microbiome_qmp](https://github.com/raeslab/temporal_variability_microbiome_qmp) |
| `/software/gbms.html` | <https://code.raeslab.org/GBMs/> |
| `/software/gmms.html` | <https://code.raeslab.org/GMMs/> |
| `/software/conet.html` | <https://apps.cytoscape.org/apps/conet> |
| `/software/lotus.html` | <https://lotus2.earlham.ac.uk/> |
| `/software/QMP/` | [raeslab/QMP](https://github.com/raeslab/QMP) |
| `/software/QMP.R` | `…/raeslab/QMP/refs/heads/master/QMP.R` (raw) |

**CoNet** and **LotuS** were only ever signposts on `raeslab.org`; both pointed at
`psbweb05.psb.ugent.be`, which is gone (404), and CoNet also at
`systemsbiology.vub.ac.be`, which no longer resolves in DNS.

- **CoNet** now points at the Cytoscape App Store, the one surviving home — the
  38 MB plugin JAR still downloads from there. Be aware that the App Store page
  itself still links to both dead sites. There is no source repository. The
  original tutorials and documentation survive only in the Internet Archive:
  <http://web.archive.org/web/2015/http://psbweb05.psb.ugent.be/conet/documentation.php>
- **LotuS** points at **LotuS2** (<https://lotus2.earlham.ac.uk/>,
  [hildebra/lotus2](https://github.com/hildebra/lotus2)), the maintained successor
  by Falk Hildebrand, who wrote the original in the lab. Note this is a newer
  tool, not the LotuS v1 the 2014 paper describes. The old v1 site is archived —
  <http://web.archive.org/web/2016/http://psbweb05.psb.ugent.be/lotus/> — but the
  archive captured only its pages, never the `lotus_*_1.40.tar.gz` or
  `sdmsource.tar.gz` packages, so v1 itself appears to be lost. The redirect goes
  to LotuS2 rather than the archive so that visitors land on software they can
  actually run.

Notes on the two that have no companion site:

- **BMT** has no GitHub Pages site, so the redirect points at the repository.
  The Zenodo deposit (<https://doi.org/10.5281/zenodo.4719508>) is the stable
  fallback if that ever moves.
- **QMP temporal** is printed in Vandeputte *et al.* (Nat Commun 2021) as
  `http://www.raeslab.org/software/QMP temporal`, with a space. The Internet
  Archive shows the real path was `/software/QMP_temporal/`, so the space is a
  typesetting artifact. A `%20` variant is deliberately *not* included, because a
  permalink containing `%` is not safe to feed to Jekyll.

### Known gaps

- **The two Tara Oceans sites are not published.** Both repositories have Pages
  configured for GitHub Actions and a correct `jekyll-gh-pages.yml` workflow
  (`source: ./docs`), but the workflow has never run, so
  `https://code.raeslab.org/Tara-Oceans-Plankton-{Interactome,Networks}/` return
  404. Until someone triggers that workflow, the redirects above deliberately
  point at the repositories and at GitHub raw URLs, which do work. Once the sites
  are live, the two page-level redirects can be switched over.
- **`/companion/gutsequencedb/` — to decide.** The Gut Sequence Database was a
  real in-house resource, not a signpost: 823 annotated human gut reference
  genomes compiled from the HMP reference collection (accessed 18 March 2018),
  served as FASTA and GenBank, plus `project_catalog.csv` covering 745 of them
  and a copy of the IGC gene catalog. **Its data files are gone.** The Internet
  Archive captured the HTML pages
  (<http://web.archive.org/web/2019/http://www.raeslab.org/companion/gutsequencedb/index.html>)
  but never the files under `data/`, so unless the lab still has them the
  downloads cannot be restored. The upstream sources it was built from are both
  still live: the [HMP reference genome catalog](https://www.hmpdacc.org/hmp/catalog/)
  and [NCBI BioProject 28331](https://www.ncbi.nlm.nih.gov/bioproject/28331).
  No redirect is in place; it falls through to the 404 page for now.
- Old URLs found in the archive with **no** migrated home yet:
  `/software/omixer.html`, `/software/gomixer.tar.gz` and
  `/software/COVID19_respiratory_microbiome/`. They currently fall through to the
  404 page. (`omixer` is being dealt with separately.)

`/software/QMP.R` points at a `raw.githubusercontent.com` URL pinned to the
`master` branch, so it serves the file itself rather than GitHub's HTML view —
which is what the printed link promised. It will follow any future change to that
file, and will break if the branch is ever renamed.
- Deep file links that exist in the archive but are not individually redirected:
  the `fgfp-gwas`, `vlaams_darmflora_project` and `suppdata` table/figure sets.
  Their landing pages are redirected, so visitors reach the right site but have
  to pick the file themselves.

## Repository layout

```
raeslab-redirect/
├── README.md              this file (not published)
└── docs/                  the published site (GitHub Pages source)
    ├── _config.yml        Jekyll config, enables jekyll-redirect-from
    ├── CNAME              custom domain: raeslab.org
    ├── index.html         redirect for the root of raeslab.org
    ├── 404.html           catch-all for unknown paths (VIB-styled)
    ├── assets/            vendored font, logo and icons for 404.html
    │   └── README.md      where they came from and under which licence
    └── redirects/         one small file per redirect
        ├── BMIS.md
        ├── companion/              companion-site landing pages
        ├── ocean-carbon-export/    Guidi et al. data files
        ├── ocean-interactome/      Lima-Mendez et al. tables and figures
        └── software/               /software/ pages and data files
```

## How it works

Each file in `docs/redirects/` contains only front matter:

```yaml
---
permalink: /software/BMIS/
redirect_to: https://code.raeslab.org/BMIS/
---
```

When GitHub Pages builds the site, the plugin turns it into
`software/BMIS/index.html`, a page with an instant meta refresh, a JavaScript
redirect, and a `canonical` link to the target. That page is served for:

- `https://raeslab.org/software/BMIS/`
- `https://raeslab.org/software/BMIS/index.html`
- `https://raeslab.org/software/BMIS` (GitHub Pages adds the trailing slash itself)

GitHub Pages cannot send real HTTP 301 redirects. Google treats an instant meta
refresh as a permanent redirect, so the SEO impact is minimal.

## Adding a redirect

1. Create a new file in `docs/redirects/`, e.g. `docs/redirects/BMT.md`:

   ```yaml
   ---
   permalink: /software/BMT/
   redirect_to: https://code.raeslab.org/BMT/
   ---
   ```

   The file name doesn't matter, but naming it after the tool keeps things tidy.
   Every `permalink` must be unique.

2. Should the permalink point to a file instead of a folder (e.g. an old
   `/downloads/tool.zip` or `/page.php`), use the exact path:

   ```yaml
   ---
   permalink: /software/old_page.html
   redirect_to: https://code.raeslab.org/new_page/
   ---
   ```

3. Several old URLs can point to the same target with `redirect_from`:

   ```yaml
   ---
   permalink: /software/BMT/
   redirect_from:
     - /BMT/
     - /tools/BMT/
   redirect_to: https://code.raeslab.org/BMT/
   ---
   ```

4. Commit and push. GitHub rebuilds the site in a minute or two
   (see the **Actions** tab for progress).

## One-time setup

### 1. GitHub repository

1. Push this repository to GitHub (e.g. `github.com/raeslab/raeslab-redirect`).
   The repository must be public, unless your organisation has a paid plan.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*,
   select branch `main` and folder `/docs`, and click **Save**.
4. Under **Custom domain**, enter `raeslab.org` and click **Save**
   (this matches the `docs/CNAME` file).
5. Once the DNS check passes and the certificate is issued (this can take up
   to an hour or so), tick **Enforce HTTPS**.

Recommended: verify the domain for your organisation
(**Organisation settings → Pages → Add a domain**) so nobody else can claim
`raeslab.org` on GitHub Pages. This adds a TXT record to the DNS.

### 2. DNS at the registrar of raeslab.org

Point the apex domain to GitHub Pages with these records:

| Type  | Name              | Value                       |
|-------|-------------------|-----------------------------|
| A     | `@` (raeslab.org) | `185.199.108.153`           |
| A     | `@`               | `185.199.109.153`           |
| A     | `@`               | `185.199.110.153`           |
| A     | `@`               | `185.199.111.153`           |
| AAAA  | `@`               | `2606:50c0:8000::153`       |
| AAAA  | `@`               | `2606:50c0:8001::153`       |
| AAAA  | `@`               | `2606:50c0:8002::153`       |
| AAAA  | `@`               | `2606:50c0:8003::153`       |
| CNAME | `www`             | `raeslab.github.io.`        |

With the `www` record in place, GitHub redirects `www.raeslab.org` to
`raeslab.org` automatically.

#### Coexisting with code.raeslab.org

The organisation site (`raeslab/raeslab.github.io`) already uses the custom
domain `code.raeslab.org`. This repository is a separate *project* site with
its own custom domain (`raeslab.org`), which GitHub Pages supports:

- `code.raeslab.org` keeps its existing CNAME record → `raeslab.github.io`.
  Leave it as it is.
- `raeslab.org` (A/AAAA records above) is served by this repository because
  of `docs/CNAME`. GitHub picks the right site based on the domain name.
- Other project repos without their own custom domain (e.g. `raeslab/BMIS`)
  stay at `code.raeslab.org/<repo>/`, as before.
- Without a custom domain this repository would appear at
  `code.raeslab.org/raeslab-redirect/`. Setting `raeslab.org` as its custom
  domain moves it off there.

Notes:

- Remove any other existing A/AAAA records for `@` and `www` (e.g. from the old
  web host), otherwise some visitors end up at the old server.
- Do **not** touch records for other subdomains, in particular `code.raeslab.org`,
  which the redirects point to.
- Don't use wildcard records (`*.raeslab.org`) pointing to GitHub.
- Check the GitHub docs for the current IP addresses:
  <https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site>

Check the DNS once it has propagated:

```bash
dig raeslab.org +noall +answer -t A
dig www.raeslab.org +noall +answer
```

## Testing locally (optional)

With Ruby installed:

```bash
cd docs
bundle init
bundle add github-pages --group jekyll_plugins
bundle exec jekyll serve
```

Then open <http://localhost:4000/software/BMIS/>.

## Keep in mind

- Keep `raeslab.org` registered and auto-renewing. If the domain lapses, every
  printed link breaks, or someone else can buy it.
- Search engines see a 404 status for paths caught by `404.html`, so give every
  URL that appears in a paper its own file in `docs/redirects/`.
- `404.html` does not redirect on its own: it explains that the link is out of
  date and offers the lab site and `code.raeslab.org`. Visitors choose where to
  go, so nobody is pulled away mid-read.
- It is styled after the VIB website, with the font, logo and icons vendored
  into `docs/assets/` so the page loads nothing from third-party servers. See
  `docs/assets/README.md` before swapping any of them out.
