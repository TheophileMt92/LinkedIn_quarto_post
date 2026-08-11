# Reproducible reporting with Quarto

A working demonstration of the report template I build for research groups and public agencies through [DataSphere Analytics](https://theophile-mouton.com).

**[View the rendered report](https://theophilemt92.github.io/LinkedIn_quarto_post/)**

## What this shows

A single `.qmd` file producing a self-contained HTML report with:

- a custom visual identity (CSS plus two HTML fragments, no Bootstrap theme)
- an interactive chart built with `plotly`, filterable by category
- a `leaflet` map with switchable basemaps, grouped layers and popups
- a sortable, searchable `reactable` table with in-cell bars

Everything is generated at render time. There is no manual assembly, and re-running the file with new data reproduces the document exactly.

## Repository contents

```
.
├── demo_report.qmd          # the report source
├── index.html               # rendered output (served by GitHub Pages)
└── Quarto_template/
    ├── custom.css           # typography, colour tokens, tables, code blocks
    ├── header.html          # ocean banner
    └── footer.html          # footer banner
```

## Reproducing it

Requires [Quarto](https://quarto.org) and R with `dplyr`, `plotly`, `leaflet`, `reactable` and `htmltools`.

```bash
quarto render demo_report.qmd
```

## Adapting the template

All colours are CSS custom properties at the top of `custom.css`:

```css
:root {
  --ocean-deep:    #062d4a;
  --ocean-mid:     #0d4f7a;
  --ocean-surface: #1a7fa8;
  --ocean-light:   #4eb8d4;
  --ocean-foam:    #c8eaf4;
}
```

Changing those values and editing `footer.html` produces a different institutional identity without touching any analysis code.

## Data

The report uses a small selection of large marine protected areas, with rounded areas and indicative centroids compiled for demonstration purposes only. Source: Protected Planet, UNEP-WCMC and IUCN. The figures are illustrative and should not be cited.

## Licence

Code and template released under the MIT Licence. See `LICENSE`.

## Contact

Théophile L. Mouton, marine conservation scientist and data consultant.
[theophile-mouton.com](https://theophile-mouton.com)
