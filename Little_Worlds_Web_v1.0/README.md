# Little Worlds Web v1.0 — Aotearoa Digital Ecology Sandbox

A browser-native, no-install educational ecosystem simulator developed as an experiment in AI-assisted software creation in 2026.

## What you get

- **Interactive sandbox:** native kiwi and wētā, introduced rats and stoats, human settlers, vegetation, fungi, microbes, rain, seasons, pond flooding, food webs, births, deaths, simplified genetics, settlements and habitat restoration.
- **Responsive habitat:** coloured map overlays (vegetation, moisture, predator pressure, human development), click to inspect or intervene.
- **Resizable layout:** drag the divider between the habitat and the journal, or between the left pane and dashboard on desktop; collapse the dashboard to focus on the world.
- **Always-visible charts:** populations, habitat trends and settlement/resource history.
- **Journal:** main feed, critical events and ecology help & tips.
- **Investigable alerts:** click a notification to learn why it matters and highlight relevant locations.
- **Creature inspector:** species illustration, diet, predators, health, energy, parents, generations and traits.
- **Offline and private saves:** all sandbox processing runs locally in your browser, with autosave to `localStorage`, manual JSON export/import and new world controls.

## Run it locally

Open `index.html` in a modern browser, or serve the folder with `python -m http.server 8000` and visit `http://localhost:8000`.

No Python packages, backend, database or API key are required. An internet connection is only needed to retrieve the website files from your host.

## Publish free on GitHub Pages

1. Create a public GitHub repository, for example `little-worlds-web`.
2. Upload **the contents of this folder**, including `index.html`, `styles.css`, `app.js` and `assets/`, at the repository root.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**, branch **main**, folder **/(root)**. Click Save.
5. The website will be available at `https://YOUR-USERNAME.github.io/little-worlds-web/` after GitHub deploys it.
6. To embed it in Wix or Google Sites, use their **Embed a Site / URL embed** feature and paste that Pages URL. Include a full-screen link for small viewports.

**GitHub Pages is static hosting:** visitors each run an *independent sandbox*. There is no shared 24/7 authoritative world in v1.0. A shared observatory requires a separate scheduled simulation, published snapshots and management of persistence.

## Controls

- **Inspect:** select creature. Click again to inspect another individual.
- **Interventions:** change rainfall, temperature, sunlight, metabolism; introduce species, plant, fertilise, create fungi, build houses, restore habitat, remove invasive predators.
- **Human policies:** Balanced, Conservation, Expansion.
- **Time controls:** pause and choose 1×, 2×, 4× or 8×.
- **Save:** autosaves per browser; JSON export to back up or share an experiment. Clearing browser storage may remove local saves.
- **Map layers:** Natural, Vegetation, Moisture, Predator pressure, Human development.

## Relationship to desktop edition

This is a **new JavaScript adaptation** of the Python/Tkinter Little Worlds v0.6 concept, not a byte-for-byte port of its simulation equations. It preserves the main educational systems and key interactions but the exact outcomes, tuning and save formats differ. Desktop JSON saves are **not compatible** with Web v1.0. Web save JSONs can be imported/exported within this edition.

### Media

The bundled creature images are **illustrated offline cards**, not verified wildlife photographs. Replace `assets/kiwi.png`, `weta.png`, `rat.png`, `stoat.png`, and `human.png` with your own appropriately licensed photos if desired (retain filenames).

## Educational and technical limitations

This simulation is deliberately stylised. Lifespans, breeding, predator behaviour, reproduction, seasons and human resource economics are abstractions. It is **not scientifically calibrated** for New Zealand ecology; it is not appropriate for forecasting wildlife management outcomes. Generated alerts identify modeled thresholds, not professional conservation assessments.

This initial edition targets modern Chrome, Firefox, Safari and Edge. For crowded ecosystems or very long unattended tabs, browsers may throttle background processing, and local storage capacity can vary. The ecological clock runs while the page is open; it does not progress after the page closes.

## Suggested next milestones

- Shared persistent read-only observatory with scheduled simulation updates and public snapshots.
- More realistic habitat zones, predator territories and ecological relationships.
- Real licensed wildlife photography with citations/credits.
- Ecological experiment templates, CSV exports and teacher activities.
- More performance profiling and responsive accessibility improvements.

## Project context

Little Worlds is a human-directed AI-assisted software-development experiment begun in 2026. It is intended to explore the capabilities and limitations of iterative natural-language software development, while making systems thinking, ecological balance and human impacts more approachable.
