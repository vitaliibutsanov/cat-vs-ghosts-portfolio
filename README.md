# Cat vs Ghosts

<p align="center"><strong>🇬🇧 English</strong> · <a href="README.pl.md">🇵🇱 Polski</a> · <a href="README.ru.md">🇷🇺 Русский</a> · <a href="README.ua.md">🇺🇦 Українська</a></p>

<p align="center">
  <img src="assets/hero.webp" alt="Cat vs Ghosts" width="100%">
</p>

<p align="center"><strong>2D desktop platformer · Python · pygame-ce · custom level editor · Windows</strong></p>

**Cat vs Ghosts** is a completed 2D platformer developed as a long-form personal Python project. What began as a small prototype grew into a full Windows game with a multi-stage campaign, profiles and saves, localization, custom content tooling, performance calibration, GPU-focused optimization work, and a release pipeline.

> **Status:** v1.0.0 — Windows desktop build completed and tested on both older hybrid-GPU hardware and a modern NVIDIA laptop.

> **Source policy:** the production repository is private. This public repository is a portfolio showcase and intentionally does not publish the complete game or level-editor implementation.

> **Role:** Project owner / Python developer — gameplay systems, custom level-editor tooling, performance profiling and optimization, localization integration, and the Windows packaging/release pipeline.

## Gameplay

The campaign moves through visually distinct environments rather than reusing one tileset or background system.

<table>
  <tr><td width="50%"><img src="assets/gameplay/stage-1-forest.webp" alt="Cat vs Ghosts Stage 1 forest gameplay"></td><td width="50%"><img src="assets/gameplay/stage-2-storm.webp" alt="Cat vs Ghosts Stage 2 storm gameplay"></td></tr>
  <tr><td align="center"><b>Stage 1 · Forest</b></td><td align="center"><b>Stage 2 · Storm</b></td></tr>
  <tr><td><img src="assets/gameplay/stage-3-swamp.webp" alt="Cat vs Ghosts Stage 3 swamp gameplay"></td><td><img src="assets/gameplay/stage-4-city.webp" alt="Cat vs Ghosts Stage 4 city gameplay"></td></tr>
  <tr><td align="center"><b>Stage 3 · Swamp</b></td><td align="center"><b>Stage 4 · City</b></td></tr>
  <tr><td><img src="assets/gameplay/stage-5-space.webp" alt="Cat vs Ghosts Stage 5 space gameplay"></td><td><img src="assets/gameplay/stage-6-castle.webp" alt="Cat vs Ghosts Stage 6 night castle gameplay"></td></tr>
  <tr><td align="center"><b>Stage 5 · Space</b></td><td align="center"><b>Stage 6 · Night Castle</b></td></tr>
</table>

## Key features

- Multi-stage platforming campaign with distinct visual themes and bosses
- Custom level editor used to build and revise the campaign
- Object-layer / brush registry for reusable gameplay and decorative objects
- Player profiles, campaign progression, save/load flow, settings and screenshots
- Keyboard and mouse UI navigation with a **last-input-wins** interaction model
- Localization in **English, Polish, Russian and Ukrainian**
- Automatic runtime performance calibration for different hardware classes
- Performance-oriented rendering work, including optimized background pipelines
- Windows desktop packaging with **PyInstaller** and installer integration
- Development-only profiling tools excluded from the final packaged build

## Custom level editor

The editor became one of the most important parts of the project. It is used for real campaign content rather than only small test rooms.

<table>
  <tr><td width="50%"><img src="assets/editor/city-overview.webp" alt="Cat vs Ghosts city level overview in the custom editor"></td><td width="50%"><img src="assets/editor/space-overview.webp" alt="Cat vs Ghosts space level overview in the custom editor"></td></tr>
  <tr><td align="center"><b>City level overview</b></td><td align="center"><b>Space level overview</b></td></tr>
</table>

<p align="center">
  <img src="assets/editor/editor-demo.gif" alt="Cat vs Ghosts custom level editor demonstration" width="100%">
</p>

<p align="center"><em>Editor demo - zoom levels, navigation, object editing, and large-map overview.</em></p>
<p align="center"><a href="assets/editor/editor-demo.mp4">▶ Watch MP4 demo</a></p>

The editor workflow includes zoom levels, large-map navigation, reusable brushes, decorative and gameplay entities, object anchors, background/theme selection, and direct testing of edited stages. The object layer is registry-driven so new content can be added without turning every level into a collection of one-off hard-coded cases.

## Tech stack

| Area | Technology |
| --- | --- |
| Language | Python 3.10 |
| Game framework | pygame-ce 2.5.2 |
| Numerical helpers | NumPy 2.2.6 |
| Packaging | PyInstaller |
| Windows installer | Inno Setup |
| Version control | Git / GitHub |
| Target platform | Windows |

## Engineering highlights

### Hardware-aware performance work
The game includes an automatic benchmark/calibration stage that measures rendering and logic workloads and stores a local performance profile. Performance work was tested on both modern hardware and an older laptop with hybrid Intel/NVIDIA graphics. The Windows release was also verified on a laptop with an NVIDIA RTX 3060, confirming that the packaged game used the discrete GPU.

### Content pipeline
Objects are described through a registry instead of being hard-coded individually into level text. Brush metadata can include asset references, anchors, gameplay roles and performance-related information.

### Release/debug separation
The PyInstaller build explicitly excludes development-only profiler modules while bundling the runtime assets and levels required by the release.

### Localization and player data
The game supports EN / PL / RU / UA through a keyed translation system with English fallback. Profiles, saves, campaign progression and settings are stored outside the packaged application.

## Project status
**Cat vs Ghosts 1.0.0** is complete. This repository is a public portfolio showcase; the production source code and Windows build are not distributed here.

## Author
**Vitalii Butsanov**
Python developer / personal software projects

GitHub: [vitaliibutsanov](https://github.com/vitaliibutsanov)

## License
This showcase is provided under a custom proprietary portfolio license. See [LICENSE](LICENSE) for the terms.
