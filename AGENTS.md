# AGENTS.md — shop-topo-site (GitHub Pages)

## Purpose

Static **GitHub Pages** bundle: human-facing `shop_viz.html` + `map.html`, My Maps KML, and small **LLM-first** artifacts (`status.json`, `shop_spec.json`, `LLM_OVERVIEW.md`).

## Do not edit by hand

- **`docs/shop_viz.html`**, **`docs/map.html`**, **`docs/parcel_and_setbacks_mymaps.kml`**, **`docs/status.json`**, and optional **`docs/shop_spec.json`** are **generated or copied** from the Shop topo workspace.
- Change the **source repo** (`generate_viz.py`, `shop_spec.json`), run `python generate_viz.py`, then run **`publish_pages.ps1`** from that repo, then commit here.

## File map

| Path | Role |
|------|------|
| `docs/index.html` | Landing page with links for humans + machines |
| `docs/shop_viz.html` | Full report (large) |
| `docs/map.html` | Folium map (iframe target) |
| `docs/parcel_and_setbacks_mymaps.kml` | Google My Maps / Earth import |
| `docs/status.json` | Compact metrics (`shop-topo-status/v1`) |
| `docs/shop_spec.json` | Canonical geometry when published |
| `docs/LLM_OVERVIEW.md` | This site’s LLM read order |
| `docs/.nojekyll` | Disables Jekyll processing on Pages |

## Pages setup

Repository **Settings → Pages**: deploy from branch **`main`**, folder **`/docs`**. Site URL: `https://<user>.github.io/<repo>/`.
