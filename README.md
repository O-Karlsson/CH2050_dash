# Child Health 2050 Data Dashboard

Interactive dashboard tracking five key child and adolescent health indicators
across countries, and their prospects for halving the gap to the best observed
value by 2050.

**Live:** https://omarkarlsson.com/CH2050_dash/

> Note: this dashboard is currently presented as a work in progress from the
> Child Health 2050 project, ahead of a future external-use version.

## What it shows

Five key indicators, each with recent levels, 5- and 10-year trends, and
projected prospects for 2050:

- Neonatal mortality
- Mortality 1–59 months
- Mortality 5–19 years
- Height gap
- Math gap

Views include per-indicator trend figures, combined summaries, star diagrams,
and a probability-of-premature-death (PPD) country ranking table.

## Data

`data/*.csv` are **aggregated, analysis-ready outputs** — country/year/sex level
summaries. No individual-level or otherwise restricted microdata is in this
repository, and none should ever be committed to it.

Full source citations are in [References.md](References.md): DHS, GBD 2023 (IHME),
and the Human Mortality Database.

The Stata/R scripts that build these CSVs from raw microdata are kept outside
this repository, since the inputs cannot be redistributed.

## Running it

Plain static HTML, CSS and JavaScript — no build step and no package manager.
Serve the directory over HTTP and open `index.html`; opening the file directly
via `file://` will not work, because the browser blocks the CSV fetches.

```
python -m http.server 8000
```

Third-party libraries (d3 v7, noUiSlider) are vendored in
`offlineLib/` rather than loaded from a CDN, so the dashboard works offline and
does not depend on external hosts staying up.

## Related

- [CIH_dash](https://github.com/O-Karlsson/CIH_dash) — sibling dashboard for the
  Lancet Commission on Investing in Health
- [omarkarlsson.com](https://omarkarlsson.com/) — portfolio site that links both
