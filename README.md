# USecVisLib Gallery

Every template in [USecVisLib](https://github.com/vulnex/usecvislib), rendered with every engine, view and style preset.

**Browse it:** https://vulnex.github.io/usecvislib-gallery/

| # | Module | What you'll find |
|---|--------|------------------|
| 01 | Attack Trees | Graphviz and SVG engine renders, all `at_*` / `sv_*` presets |
| 02 | Threat Modeling | DFDs with the usecvislib, pytm and SVG engines, all `tm_*` / `sv_*` presets |
| 03 | Binary Visualization | Entropy, distribution, wind rose and heat map with default and custom configs, all `bv_*` presets |
| 04 | Attack Graphs | Graphviz and SVG engine renders, all `ag_*` / `sv_*` presets |
| 05 | Custom Diagrams | Every template category, all `cd_*` presets |
| 06 | Cloud Diagrams | AWS, Kubernetes and zero-trust templates, top-to-bottom and left-to-right |
| 07 | Mermaid | Every Mermaid template in the default and dark themes |
| 08 | Privilege Gradient | All templates, all `pg_*` presets |
| 09 | Component Diagram | Graphviz and SVG engine renders, all presets |
| 10 | Dependency Graph | Graphviz and SVG engine renders, all presets |
| 11 | Kill Chain | Graphviz and SVG engine renders, all `kc_*` / `sv_*` presets |
| 12 | Incident Timeline | Swimlane, Gantt, vertical and compact views, Matplotlib and SVG engine |
| 13 | Vulnerability Tree | Tree, vulnerable-only and critical-path views |
| 14 | MAESTRO | Layered, graph and heat map views, all `ma_*` / `sv_*` presets |
| 15 | Shine Pack | Graphviz SVG output post-processed with `--shine` |

Each folder has the PNG, SVG, PDF and (for Graphviz) DOT output, so you can compare engines and formats side by side.

## Rebuilding

The gallery is generated, not hand-edited. From a USecVisLib checkout, with the API Docker image built:

```bash
docker run --rm -v "$PWD":/repo -v /path/to/usecvislib-gallery:/out -w /repo \
  -e PYTHONPATH=/repo/src -e PYTHONHASHSEED=0 --entrypoint python usecvislib-usecvislib-api \
  scripts/build_gallery.py /out
```

The script keeps this README, the LICENSE and dotfiles, replaces everything else, and fails if any render errors or if an output contains a home-directory path or an e-mail address.

## License

Apache-2.0. Copyright (c) 2026 VULNEX. https://www.vulnex.com
