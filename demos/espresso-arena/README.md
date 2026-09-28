# Espresso Arena

Published at https://patrickrjordan.com/demos/espresso-arena/.

`index.html` is the complete interactive presentation: replicator dynamics, Nash-based empirical game-theoretic analysis (EGTA), and five buyer encounters before and after strategy exploration. It includes its data, JavaScript, and styles and requires no backend, model runtime, or external assets.

The results come from a saved study, including cached real Laya model responses and learned public-input best-response policies. The page performs no live model inference, training, or equilibrium solving.

## Updating the demo

1. In the Espresso Arena research repository, run `uv run --frozen --extra training python -m backend.export_static` after validating the saved study.
2. Copy the generated `presentation/espresso-arena.html` here as `index.html`, preserving its bytes.
3. Copy the generated manifest here as `manifest.json` and change only its `file` field to `index.html`.
4. Confirm the HTML SHA-256 matches `html_sha256` in the manifest.
5. Commit and merge to `main`; the existing GitHub Pages deployment serves this directory directly.

Do not transform or minify the HTML during deployment: its content security policy verifies the embedded JavaScript by hash. The manifest records artifact integrity and study provenance; it is not needed to load the page.
