# LITTLE WORLDS
## Development & Technical Documentation Report
**Release documented:** v0.6  
**Project type:** Educational desktop ecosystem simulation / experimental digital pet  
**Documentation date:** 10 October 2026

### Executive summary

Little Worlds began as a compact, autonomous desktop terrarium inspired by the Tamagotchi concept, but with interdependent populations and ecological processes instead of one virtual pet. Across eight packaged iterations—from the initial proof of concept to v0.6—the project evolved from a simple fictional food chain into an educational, New Zealand-inspired simulation of native and introduced species, human development, environmental interventions, historical trends and ecological warnings. User feedback drove the direction: visible rainfall effects, readable event narration, individual-creature inspection, richer human agency, permanently available graphs, actionable alerts, and finally resizable panels.

The application is written in Python using the standard-library Tkinter UI toolkit. It can run offline and persists worlds in local JSON files. Its ecological and human-behaviour systems remain deliberately simplified. Accordingly, this report documents the application as a playable teaching prototype rather than a validated scientific simulator.

### 1. Project origin and objectives

The initial concept was **a miniature simulated world that lives in a desktop window**, in which weather, vegetation, animals, fungi and microorganisms interact. The user could alter physical conditions, add organisms, intervene in ecological issues or observe the world unfold autonomously. The desired emotional effect was an “overly complex and realistic Tamagotchi”: attachment not only to creatures but to the changing ecosystem itself.

The project developed four complementary goals: (1) autonomous emergent behaviour, (2) meaningful human intervention, (3) educational visibility into why ecological changes happen, and (4) the aesthetic charm and accessibility of a small desktop application. The New Zealand setting was selected to give the simulation recognisable real-world relationships, such as the pressure that introduced mammals can place on native wildlife.

### 2. Scope and current capabilities

**Environment and natural processes.** The habitat is a 58 × 32 grid. Cells model plant cover, nutrients, detritus, fungus, microbes, moisture, freshwater and potential buildings. A stylised day/night cycle, accelerated seasons, temperature and rainfall influence plant production and water availability; sustained rain can expand the pond into adjacent low ground.

**Animals and people.** Brown kiwi, forest wētā, ship rats, stoats and human settlers exist as mobile agents with energy, age, thirst and health. Agents forage, move, encounter predators, reproduce, age, become ill and die. Offspring can inherit speed, efficiency, resilience and fertility values; parent identifiers and generation numbers are stored.

**Human impacts.** Human agents may build houses/villages, remove vegetation, consume shared supplies, source food/materials and carry out predator control. Policy choices—Balanced, Conservation and Expansion—alter settlement pressure and intervention frequency. Conservation work can fund revegetation sites that gradually improve local plant cover and nutrients.

**Observation and explanation.** The interface contains a creature viewer, tile inspector, ecology field guide, event journal, severity-tagged alerts, an always-accessible history graph, and tabs containing population/soil/settlement analysis. The journal distinguishes ordinary activity, critical events and help/tips. Alert investigations give explanatory context, recent metrics, proposed interventions and a current-location map highlight.

**Presentation and interaction.** v0.6 uses nested draggable panes, a collapsible right dashboard, map overlay choices for vegetation, moisture, predator presence and development, and image-ready portrait slots. Offline illustrated species cards ship with the app; verified photographs are not included.

### 3. Iterative version-by-version evolution

#### v0.1 — Foundation: a terrarium that runs itself
**Design goal.** Establish a genuinely operating ecosystem, not a decorative screensaver.  
**Implemented.** Tile-level vegetation, fungi, microbes, detritus and nutrients; fictional herbivores (Mossbacks), predators (Ember foxes) and beetles (Dusk beetles); energy, thirst and ageing; weather, day/night and seasons; temperature/rain/sunlight/metabolism controls; inspection and organism-spawning tools; local JSON save/load and autosave.  
**Significance.** Proved the full observe–intervene–observe loop could work entirely offline with Python/Tkinter.  
**Limitation identified.** The ecological simulation produced changes, but it was hard to understand *why* they happened, and pond boundaries did not react visibly to rain.

#### v0.2 — Make consequences legible
**User feedback.** Asked for a chat-like written activity panel; raising rain was killing creatures without increasing visible water.  
**Implemented.** Scrollable timestamped live feed for weather, births, deaths and important events; pond waterline expanded with prolonged rainfall and receded in dry weather; improved attempts by creatures to avoid flooded terrain and adjusted thirst/energy pressure.  
**Significance.** Connected player action to visible environmental feedback and made the simulation narrate itself.

#### v0.3 — Aotearoa and the creature viewer
**User feedback.** Wanted a portrait panel above sliders showing species information, plus a realistic NZ setting with predator–prey and human interactions.  
**Implemented.** Brown kiwi, forest wētā, ship rats, stoats and human settlers replaced the original fictional animal cast; species descriptions (food, predators, role) and creature condition were made inspectable; settlers built house/village icons on land and altered vegetation; targeted predator control became available.  
**Significance.** Shifted the project from generic simulation toward a recognisable educational case study.  
**Limitation.** Biological relationships were loosely inspired by NZ ecology, not calibrated to field measurements.

#### v0.4 — Individual lives, society and early ecological warnings
**User feedback.** Requested richer creature and human behaviour, educational ecological imbalance alerts and better UI organisation.  
**Implemented.** Heritable traits, generations/parent IDs, home-range behaviour, simplified infection and temporary immunity; human development policies (Balanced, Expansion, Conservation); ecological alerts for low populations, predator ratios, drought, habitat degradation, flooding, disease and settlement activity; an Ecology & guide tab alongside Interventions.  
**Significance.** Provided an initial basis for following individuals and prompted players to interpret systemic problems.  
**Limitation.** Alert thresholds were heuristic and the fixed sidebar increasingly crowded.

#### v0.5 — A world with history and restoration
**User feedback.** Accepted the proposal for time-series graphs and more consequential human development.  
**Implemented.** Daily history samples across species, land indicators, water and settlement resources; population/habitat/settlement chart categories; major event milestones; human resource consumption and harvesting; finite building supplies; funded restoration patches with map markers and gradual environmental benefits.  
**Significance.** Turned a transient animation into a measurable simulation: players could compare before/after patterns and test hypotheses.  
**Limitation.** History was contained within a tab and the feed/alerts remained too easy to miss.

#### v0.5.1 — Monitoring visibility
**User feedback.** Graph should remain visible; chat must show at least six lines; alerts should have their own box and appear in chat.  
**Implemented.** Always-visible live history chart in the sidebar; larger, smaller-font journal; independent ecological notifications list; daily alert assessment rather than every third day; expanded Insights coverage.  
**Significance.** Recognised that core signals must stay in view while a player acts, not be hidden behind settings.

#### v0.5.2 — Investigate, don’t merely warn
**User feedback.** Coloured legends were unclear; separate Main/Critical/Help journal tabs and allow clickable investigations.  
**Implemented.** Chart legend dots coloured to match their series; journal tabs for Main, Critical events and Help & tips; notification selection and critical-event double-click to open explanations, metric context, suggested intervention and relevant-area map highlighting.  
**Significance.** Established a lightweight inquiry workflow: detect → explain → locate → intervene → observe.  
**Limitation.** Map highlighting is heuristic; an area associated with a risk is not proof of its cause.

#### v0.6 — Flexible monitoring workspace
**User feedback.** Panels should resize; dashboard should collapse; creature viewer should better connect virtual animals with actual animals through images.  
**Implemented.** Nested resizable Tkinter panes, a collapsible dashboard, habitat scale-aware rendering and click mapping, user-selectable vegetation/moisture/predator/development map overlays, a refreshed layout and enlarged image-driven creature card viewer.  
**Media status.** Real animal photography was an aspiration, but this package ships illustrated offline PNG cards; the loader can display replacement PNGs placed in the asset directory.  
**Significance.** Shifted the application from a fixed prototype screen toward an adaptable monitoring and learning workspace.  
**Remaining work.** Layout persistence, higher-fidelity media, comprehensive accessibility and responsive testing on different screen sizes.

### 4. Requirements and design rationale

| Need discovered through iteration | Response in the design |
|---|---|
| Consequences of weather were not visible | Waterline transitions tied to rainfall; event narration |
| Too difficult to understand ecological changes | Live journal, warnings, field guide and historical charts |
| Want attachment to individual animals | Selectable creature IDs, portraits, health, heredity and family context |
| Human presence needs consequences | Resource spending, settlement construction, harvesting, conservation |
| Alerts hidden in noise | Separate notifications, critical-events journal, severity colours |
| Recommendations should be actionable | Alert investigation dialogs, highlights and intervention advice |
| Fixed panels felt overcrowded | Split-pane layout and collapsible dashboard |
| Educational link to real NZ species | Species-specific diet/threat descriptions and replaceable image slots |

### 5. Technical architecture

**Technology.** Single Python application (`terrarium.py`), Tkinter and `ttk` for interface widgets, Python dataclasses for creatures, built-in `random` for seeded stochastic events, local JSON files for persistence. The launcher is `Launch Little Worlds.bat`; the `assets/` folder supplies PNG cards. Standard-library-only runtime avoids network and third-party install requirements.

**Primary conceptual components.** `SPECIES` is a data dictionary describing current species. `Creature` is an agent dataclass. `World` holds terrain, environmental variables, creatures, events, history, settlements, restoration sites and numerical simulation rules. `TerrariumApp` constructs widgets, handles user input, draws tiles and agents, drives simulation time, and exposes saving/investigation functions.

**Simulation loop.** The GUI uses a recurring Tkinter `after` loop. Elapsed real time is converted to one or more world ticks, depending on playback speed; each tick updates weather/water, soil/plant/decomposition processes and agent behaviour. Day boundaries trigger longer-cycle human resource updates, ecological assessments and history samples. Rendering and GUI panel refresh happen periodically, not on every individual state mutation.

**Data representation.** The current world dimensions are `W=58`, `H=32`, `CELL=15` in the model, with cell dimensions used as a logical drawing basis; the v0.6 canvas scales this presentation to its available space. Creature records include identifiers, position, biological state, inherited traits and family fields. Every history sample stores day-indexed populations and environmental/human metrics. Events are retained as time-labelled strings.

**Persistence.** `World.to_dict()` serialises the main world state to JSON; `World.from_dict()` reads supported schema versions, maps older fictional species into the current setting, and supplies defaults for newly added fields. Current schema value is `SAVE_VERSION=4` (distinct from app release 0.6). Autosave is located under `.little_worlds` in the user's home directory. A backup is recommended before migrating a save to a newer release.

**Alerting.** `World.assess_ecology()` checks ratio/threshold conditions; `World.alert()` writes severity-tagged events with per-category cooldowns. The app derives the notifications list and Critical events tab from the event history. `show_alert_details()` builds an investigation with suggestions derived from `advice_for()`, while highlight overlays indicate currently relevant tiles or species. Alerts are rule-based, not AI services or authoritative ecological diagnoses.

**Media.** The creature viewer reads local PNG assets using Tkinter's `PhotoImage`, cached by species key. Image filenames are tied to species identifiers. This allows later replacement with appropriately licensed wildlife photographs, but asset provenance and crediting would need to be completed before distribution.

### 6. User experience and information architecture

The evolved interface intentionally separates four tasks: **observe** (habitat and always-visible chart), **notice** (journal and notifications), **investigate** (creature viewer, alert details, Insights and field guide), and **act** (Interventions). Earlier releases crowded these tasks into fixed sidebars, causing a feedback cycle of buried information and shrinking observation space. The v0.6 resizable layout gives users control over that trade-off.

The journal includes three parallel views of the same ecosystem: chronological narrative, filtered significant events and interpretation-oriented advice. Warnings remain present in the Main feed as well as in Critical events and Notifications, balancing visibility with the ability to focus.

### 7. Educational opportunities

Little Worlds is particularly suited to demonstrating interdependence, feedback loops, unintended consequences, species introductions, habitat disturbance, predator–prey pressure, resource constraints and the limits of simplistic interventions. A classroom exercise can establish a baseline over a set period, change a single variable, record observations, compare graphs and formulate a hypothesis. Students should be encouraged to distinguish **what the model does** from **what real ecosystems do**.

Suggested inquiry sequence: (1) observe baseline populations, (2) choose a question, (3) predict outcomes, (4) make one intervention, (5) watch live and historical indicators, (6) discuss alternative explanations and model assumptions. An ecological warning is the start of investigation, not its conclusion.

### 8. Verification, constraints and known limitations

**Verified during development.** The packaged release was checked for syntax and basic GUI operation in a virtual display; targeted tests exercised dashboard collapse/re-expand, overlay switching, creature viewer updates, and world simulation/save-load round trips. That is meaningful prototype validation but **not full Windows acceptance testing** or a performance benchmark across machines.

**Scientific fidelity.** Biological rates, seasons, lifespan duration, births, infections, water dynamics and resource use are deliberately simplified. Native and introduced species occupy coarse roles; species interactions do not reproduce measured NZ population responses. Microbes and fungi are modelled as biomass/coverage per tile rather than mobile individuals. Human decision-making is rule-based.

**Technical debt.** The project remains a relatively large single Python file; a modular package with unit tests would improve maintainability. The graph stores a bounded set of samples rather than long-term archival records. There is no multiplayer, no true offline-running simulation when the app is closed, no cloud sync, and no machine-learning component. Current species image cards are not authentic photos. Resize changes may still expose layout constraints on small screens and should be tested.

**Accessibility and clarity.** The dark UI uses small fonts in some dense panels; keyboard navigation, screen-reader semantics, colour-independent legends, font scaling, contrast testing and localisation need dedicated work. Alerts should avoid overstating cause, and the guide should link to reliable conservation material.

### 9. Proposed development roadmap

**Near term (v0.6.1 / v0.7).** Package properly attributed, licensed wildlife photos and captions; persist panel widths and overlay choice; improve responsiveness and zoom/pan; make alert entries easier to scan and dismiss; add clear colour-independent legend markers; improve performance at high speed.

**Medium term.** Distinct NZ habitat types (native forest, wetland, grassland, scrub, developed land), habitat preferences, fragmentation and migration corridors; an interactive comparison tool for ecological experiments; named and bookmarked creatures; more detailed life-event timelines; CSV export and saved experiments.

**Long term.** Improved calibrated ecological relationships with expert review, explicit assumptions and uncertainty ranges, structured scenario lessons for students, more sophisticated settlement economies, expanded endemic species, and optional comparative habitats from other regions. Scientific validity would require ecological consultation, published parameter sources and systematic calibration.

### 10. Versioning, distribution and provenance

Release identifiers `v0.1` through `v0.6` describe app iterations. The internal JSON `SAVE_VERSION` is independent; the v0.6 writer still uses schema 4. The distributable consists of source files and local image assets, not a standalone compiled executable. Players should extract the ZIP and keep launcher, code and assets together. Before distributing publicly, add an explicit project licence, contributor acknowledgements, and image/media attribution for any third-party photos used.

### 11. Concluding assessment

The most important project evolution is conceptual: Little Worlds started as something to **watch**, became something players could **affect**, and now increasingly invites players to **investigate and understand** the effects of their actions. The next challenge is to deepen the science and pedagogy without losing the approachable, delightful simplicity of a tiny desktop world.

### Appendix A — Package inventory (v0.6)

- `mini_ecosystem/terrarium.py` — simulation logic, Tkinter UI, charting, alerts and saving.
- `mini_ecosystem/Launch Little Worlds.bat` — Windows launcher.
- `mini_ecosystem/README.md` — in-package user instructions.
- `mini_ecosystem/assets/*.png` — bundled illustrated species cards.

### Appendix B — Suggested sources for future validation

- New Zealand Department of Conservation (DOC), kiwi species facts: https://www.doc.govt.nz/nature/native-animals/birds/birds-a-z/kiwi/facts/
- DOC, stoats and animal pests: https://www.doc.govt.nz/nature/pests-and-threats/animal-pests-and-threats/stoats/
- DOC, predator control programme: https://www.doc.govt.nz/predator-control-programme

These are starting points for contextual learning, not evidence that the current model has been calibrated to those sources.
