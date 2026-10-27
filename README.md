# raeslab.org redirects

This repository keeps the old `raeslab.org` URLs (as printed in papers) working by
redirecting them to their new locations. It is a small Jekyll site hosted on
GitHub Pages and uses the [`jekyll-redirect-from`](https://github.com/jekyll/jekyll-redirect-from)
plugin, which GitHub Pages supports out of the box.

| From                                  | To                                  |
|---------------------------------------|-------------------------------------|
| `https://raeslab.org/`                | `https://raeslab.sites.vib.be/`     |
| `https://raeslab.org/software/BMIS/`  | `https://code.raeslab.org/BMIS/`    |
| any other (unknown) path              | 404 page → lab homepage after 5 s   |

## Repository layout

```
raeslab-redirect/
├── README.md              this file (not published)
└── docs/                  the published site (GitHub Pages source)
    ├── _config.yml        Jekyll config, enables jekyll-redirect-from
    ├── CNAME              custom domain: raeslab.org
    ├── index.html         redirect for the root of raeslab.org
    ├── 404.html           catch-all for unknown paths
    └── redirects/         one small file per redirect
        └── BMIS.md
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
| CNAME | `www`             | `<github-org>.github.io.`   |

Replace `<github-org>` with the GitHub account or organisation that owns this
repository (e.g. `raeslab.github.io`). With the `www` record in place, GitHub
redirects `www.raeslab.org` to `raeslab.org` automatically.

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
