# shop-topo-site

Static **GitHub Pages** site for the Shop topo project: full interactive HTML report plus small JSON/Markdown files for LLMs.

## Enable GitHub Pages

1. Push this repository to GitHub.
2. **Settings → Pages → Build and deployment**: source **Deploy from a branch**, branch **`main`**, folder **`/docs`**.
3. After the first deploy, open `https://<your-username>.github.io/<repo-name>/` (GitHub shows the exact URL on the Pages settings page).

## Publish workflow (from the Shop topo workspace)

In the machine that runs Python:

```powershell
conda activate shop-topo
cd "<path-to-Shop-topo-workspace>"
python generate_viz.py
.\publish_pages.ps1
```

Then in **this** repo (or a clone of `shop-topo-site`):

```powershell
cd shop-topo-site
git add docs/
git commit -m "Publish static viz bundle"
git push
```

## Privacy

`shop_spec.json` and the report contain the property address. A **public** repository and Pages site expose that data.

## Optional env vars (workspace / `generate_viz.py`)

- **`SHOP_TOPO_GOOGLE_DRIVE_MYMAPS_DIR`** — copy `parcel_and_setbacks_mymaps.kml` into a Google Drive–synced folder on each run.
- **`SHOP_TOPO_PAGES_DOCS`** — absolute path to this repo’s `docs` folder to copy `status.json` automatically after each `generate_viz.py` run (optional; `publish_pages.ps1` still copies the full set).
