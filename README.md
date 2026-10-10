# LITTLE WORLDS
## Aotearoa Living Terrarium — User README
**Current version:** v0.6  
**Platform:** Windows desktop (Python 3.10+ / Tkinter)  
**Status:** experimental educational simulation / playable prototype  
**Last documented:** 10 October 2026

Little Worlds is an offline desktop ecosystem that behaves like an unusually complex digital pet. Watch a miniature New Zealand-inspired landscape as plants grow, organisms consume resources, predators hunt, creatures reproduce and die, weather reshapes the pond, and humans expand settlements or restore habitat. Intervene directly—or let the world run and observe the consequences.

> **Important:** This is a simplified educational game, not a scientifically calibrated ecological model or a predictor of conservation outcomes. Its fictional time scales, thresholds and agent decisions are designed for play and learning.

## 1. Install and launch

1. Download and extract `Little_Worlds_v0.6.zip`. Keep the `mini_ecosystem` folder and its contents together.
2. Install [Python 3.10+](https://www.python.org/downloads/) if needed. On Windows, a standard Python installation includes Tkinter/Tcl-Tk; selecting **Add Python to PATH** is helpful.
3. Double-click `Launch Little Worlds.bat` in the extracted folder. Alternatively, open a terminal there and run `py -3 terrarium.py` or `python terrarium.py`.
4. The world starts automatically, loading your local autosave if present.

The application uses only the Python standard library at runtime. It works offline; there are no accounts, API keys or subscriptions. It is **not** a compiled Windows `.exe` or conventional installer.

## 2. Your first five minutes

1. Watch the habitat for animal movement, vegetation changes and day/night cycles.
2. Select **Inspect** in **Interventions** and click a creature to reveal its picture card, biological role, diet, predators, health, parents and genetics.
3. Check **Live History** for population trends. Change the dropdown to inspect habitat or settlement metrics.
4. Open the journal's **Main**, **Critical events** and **Help & tips** tabs. Click an alert in **Ecological Notifications** to investigate it and optionally highlight relevant locations.
5. Try a single intervention—e.g. raise rainfall gently or plant a restoration plot—and compare subsequent changes. Extreme settings can destabilise the world.

## 3. Interface guide (v0.6)

**Habitat:** The main map shows tiled terrain, plants, fungi, weather, creatures, houses and restoration sites. Selecting a tool then clicking a tile applies that intervention. The map scales with its pane; click positions are mapped to the underlying grid.

**Map overlays:** Choose `None`, `Vegetation`, `Moisture`, `Predator pressure` or `Human development`. Overlays are visual summaries of the simulation, not geographic measurements of real NZ conditions.

**Journal:** The resizable panel below the habitat has three tabs: **Main** for activity, **Critical events** for notifications/warnings, and **Help & tips** for contextual educational guidance. Double-click a critical event to investigate it.

**Creature viewer:** Selecting an animal reveals its species card, ID, generation, parent IDs, inherited traits, energy, health, thirst, dietary preferences, predators/threats and infection status. The viewer describes individuals with stylised life cycles, not real biological measurements.

**Ecological notifications:** A separate dashboard list preserves recent critical, warning and notice events. Click one to open an investigation with explanation, recent trends and possible actions. The **Highlight affected areas** button shows currently relevant organisms or tiles; it does not prove that those locations caused the event.

**Live History:** A permanent chart in the dashboard offers three modes: populations, habitat, and settlement/resource metrics. Coloured legend markers correspond to coloured lines. Each simulated day contributes a snapshot; old saves cannot retroactively generate historical samples.

**Dashboard tabs:** **Interventions** contains settings, tools, development policy, time controls and save/load. **Ecology & guide** explains indicators and relationships. **Insights** shows expanded statistics and major milestones.

**Resizable layout:** Drag the splitters to allocate space between habitat and dashboard, habitat and journal, or dashboard monitoring and lower tabs. Use **Collapse dashboard** to dedicate more space to the world; use **Expand dashboard** to restore it. The creature viewer, notifications and graph live in the dashboard and are hidden while collapsed.

## 4. Controls and interventions

| Control | What it changes |
|---|---|
| Pause / 1× / 2× / 4× / 8× | Stops or accelerates simulated time. |
| Temperature | Offsets ambient temperature, influencing metabolism/plant growth. |
| Rainfall | Changes rain frequency, soil moisture and pond expansion/recession. |
| Sunlight | Changes light availability, affecting plant growth and the day cycle. |
| Metabolism | Changes energy consumption of creatures. |
| Inspect | Selects a nearby creature or inspects environmental conditions at a tile. |
| Seeds / Fungi / Microbes / Minerals | Adds plants, decomposers or nutrients. |
| Kiwi / Wētā / Rats / Stoats / Humans | Introduces members of the chosen population. |
| Build house | Places a human structure on suitable dry ground, using supplies. |
| Predator control | Removes introduced predators in a chosen area. |
| Restore habitat | Starts a funded revegetation patch on suitable land. |
| Human policy | Balanced, Conservation or Expansion changes construction and control behaviour. |
| Save as… / Load… | Writes/reads manual JSON world files. |

**Use `Sprinkle selected across world` with care:** it may introduce many organisms or significant material across the habitat. It is intended as a high-impact experiment, not a precision intervention.

## 5. The living system

**World grid:** 58 × 32 cells. Each tile has water status/terrain basin depth, soil moisture, nutrients, vegetation, fungi, microbial biomass, detritus and optional structures. Fungi and microbes are simulated as tile-level quantities, not individual agents.

**Weather and water:** Seasonal temperature, daylight and weather fronts affect growth and survival. Rain increases basin water level and flooding can convert terrestrial tiles into water. Dry periods gradually lower the waterline.

**Food web:** Brown kiwi forage on invertebrate-like resources and wētā; forest wētā consume vegetation and organic material; ship rats consume seeds/invertebrates and threaten young kiwi; stoats hunt rats, wētā and vulnerable young kiwi. Organisms die, leaving detritus that decomposers convert back into soil nutrients.

**Individual lives:** Creatures have IDs, age, energy, thirst, health, home ranges, inherited variation in speed/efficiency/resilience/fertility, generations and limited parent history. Infection and temporary immunity are abstract mechanics. This is not a genetic or epidemiological model suitable for research use.

**Humans:** Settlers may construct houses/villages, consume shared supplies, harvest plants and sometimes control predators. Off-map trade/production is abstracted. Development policy influences how quickly settlements spread and the frequency of interventions.

**Restoration:** Players (and sometimes conservation-minded settlements) can establish marked revegetation plots. Plant cover and nutrients gradually increase locally; the restoration budget regenerates over time.

## 6. Alerts and educational interpretation

Warnings can relate to kiwi decline/extinction, relative stoat/rat pressure, vegetation loss, drought, flooding, resource scarcity, settlement growth and infection. The simulator assesses important ecological thresholds daily and uses cooldowns to reduce repeated messages. Warning colours and classifications are game heuristics—not verified real-world risk levels.

To investigate, open a notification, read the explanation and trend comparison, highlight relevant areas, decide on an intervention, and watch the graph for subsequent changes. A population recovery after intervention does **not** establish causation; multiple systems interact.

## 7. Saving, privacy and portability

Autosaves are written roughly once per minute and on ordinary program exit to `%USERPROFILE%\.little_worlds\autosave.json` on Windows. Manual saves use JSON files chosen by the player. Saving is local only; there is no cloud sync or telemetry in the current code.

**Back up your autosave before upgrading.** The current save writer uses schema/version `4` and supports earlier schema versions `1–3` as well as `4`. Older application versions may not read newer saves. History begins recording in the version that first adds it; missing older trends are not reconstructed.

## 8. Creature images and credits

v0.6 includes **illustrated offline species image cards**, stored in `mini_ecosystem/assets/kiwi.png`, `weta.png`, `rat.png`, `stoat.png` and `human.png`. These are **not real wildlife photographs**. You can supply a suitable, licensed PNG photo at the same filename to replace a card. Keep the images modest in size (the viewer currently loads PNGs via Tkinter's `PhotoImage`) and document image sources/credits for any redistributed replacement photography.

## 9. Troubleshooting

| Problem | Try this |
|---|---|
| Batch launcher closes or Python isn't recognised | Install Python 3.10+ and enable PATH, or run `py -3 terrarium.py` from a terminal to see errors. |
| Window feels cramped | Maximise the window; drag splitters; collapse the dashboard when exploring. |
| No alert visible | Warnings appear only when thresholds are reached; check Critical events and simulate several days. |
| Creature selection is difficult | Select Inspect; click near a visible sprite; pause or slow simulation first. |
| Population crashes after extreme rain | Reduce rainfall; allow water to recede; check habitat area and food availability before reintroducing animals. |
| Photo doesn't appear | Use a valid PNG at the matching `assets/<species>.png` path and restart the app. |
| Save behaves unexpectedly | Back up `autosave.json`, use Save as… to make an independent copy, and avoid opening the same save in older releases. |

## 10. Version history

| Version | Main contribution |
|---|---|
| v0.1 | First playable terrarium: fictional food web, plants/decomposers, weather, controls, saves. |
| v0.2 | Live event journal, changing pond size, survival/flooding adjustments. |
| v0.3 | NZ-inspired species and human settlers; creature viewer; houses/villages and predator control. |
| v0.4 | Genetics, family history, home ranges, infection; development policies; ecological warnings and guide tabs. |
| v0.5 | Daily history, graphs and milestones; human supplies/harvesting; restoration budget and plots. |
| v0.5.1 | Visible chart in sidebar; larger feed; separate notifications and daily checks. |
| v0.5.2 | Coloured chart legends; Main/Critical/Help journal tabs; clickable alert investigations and map highlights. |
| v0.6 | Resizable nested panes, collapsible dashboard, habitat overlays, image-ready creature viewer, visual refresh. |

For full context, technical details, design decisions and a future roadmap, see **Little_Worlds_Development_Report.docx** and **Little_Worlds_Development_Report.md**.
