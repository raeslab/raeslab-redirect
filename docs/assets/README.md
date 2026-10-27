# Vendored assets

Everything the 404 page needs is stored here, so the page renders with no
external requests (no Google Fonts, no calls back to `vib.be`). Sources and
licences:

| File | Source | Licence / note |
|------|--------|----------------|
| `fonts/nunito-sans-latin.woff2` | [Google Fonts](https://fonts.google.com/specimen/Nunito+Sans), latin subset, variable (wght 200–1000) | SIL Open Font License 1.1 — free to self-host |
| `img/arrow.svg` | VIB `entityone` theme, `_global/images/geom3.svg` | VIB asset, used with permission |
| `img/arrow-dark.svg` | VIB `entityone` theme, `_global/images/geom3-dark.svg` | VIB asset, used with permission |
| `img/raeslab-logo.png` | `raeslab.sites.vib.be/.../CfM-Lab-logo_raes-blue.png` | Lab logo |

Downloaded 2026-10-27 from `https://raeslab.sites.vib.be/`.

## Not vendored: Degular

The VIB theme sets **Degular** for headings. It is an Adobe Fonts (Typekit)
licence delivered through VIB's own kit (`use.typekit.net/hva5mzp.css`), which
is domain-locked to VIB sites — it would not load on `raeslab.org`, and
self-hosting it is not permitted by that licence. The 404 page uses Nunito Sans
at weight 500 for headings instead, which is what the VIB theme itself falls
back to.

If the lab has a Degular licence covering `raeslab.org`, drop the webfont files
in `fonts/` and change the `h1, h2` rule in `../404.html`.

## Theme tokens

Copied from the live theme's `_global/global.css`:

```
--primary-color:          #00264F
--secondary-color:        #1cbbba
--tertiary-color:         #A0B2D4
--quarternary-color:      #2A529E
--background-color-light: #ECF4F8
--background-color-dark:  #00254F
```

Body text is Nunito Sans 300 / line-height 1.42; buttons are uppercase 600 with
the geometric arrow that widens from 6px to 18px on hover.
