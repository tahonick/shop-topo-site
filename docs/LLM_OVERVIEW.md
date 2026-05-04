# Shop topo — LLM overview (published site)

## Read order

1. **`status.json`** — Small JSON (`shop-topo-status/v1`): decision flag, pad center (local ft), dimensions, primary scenario label, driveway/house headline metrics, binding constraint summary from the last `generate_viz.py` run.
2. **`shop_spec.json`** — Canonical geometry and tree list when copied by the publish script. Numbers in HTML tables should match this file; if they disagree, **trust `shop_spec.json`**.
3. **`shop_viz.html`** — Full human UI (Plotly 3D, embedded Folium `map.html`, long narrative). Large; fetch only after the two JSON files above.

## Source of truth (development repo)

The interactive site is a **static snapshot** built from the private or local “Shop topo” workspace:

- Generator: `generate_viz.py`
- Spec validator: `validate_spec.py` (expect **12 passed** after editing `shop_spec.json`)

Re-publish by running `python generate_viz.py`, then `publish_pages.ps1` from the workspace root, then commit and push this `shop-topo-site` repository.

## GitHub raw URLs

After push, LLMs can use stable raw links:

- `https://raw.githubusercontent.com/<YOUR_USER>/<REPO>/main/docs/status.json`
- `https://raw.githubusercontent.com/<YOUR_USER>/<REPO>/main/docs/shop_spec.json`

Replace `<YOUR_USER>` and `<REPO>` (e.g. `shop-topo-site`).

## My Maps

`parcel_and_setbacks_mymaps.kml` is for **Google My Maps / Earth** import. My Maps does not auto-refresh from Drive; when the KML changes, **re-import** or update the layer in the My Maps UI.
