# Cat vs Ghosts

<p align="center">
  <img src="assets/hero.webp" alt="Cat vs Ghosts main menu showing multiple game worlds" width="100%">
</p>

<p align="center">
  <strong>2D desktop platformer · Python · pygame-ce · custom level editor · Windows</strong>
</p>

**Cat vs Ghosts** is a completed 2D platformer developed as a long-form personal Python project. What began as a small prototype grew into a full Windows game with a multi-stage campaign, profiles and saves, localization, custom content tooling, performance calibration, GPU-focused optimization work, and a release pipeline.

> **Status:** v1.0.0 — Windows desktop build completed and tested on both older hybrid-GPU hardware and a modern NVIDIA laptop.

> **Source policy:** the production repository is private. This public repository is a portfolio showcase and intentionally does not publish the complete game or level-editor implementation.

## Gameplay

The campaign moves through visually distinct environments rather than reusing one tileset or background system.

<table>
  <tr>
    <td width="50%"><img src="assets/gameplay/stage-1-forest.webp" alt="Forest stage gameplay"></td>
    <td width="50%"><img src="assets/gameplay/stage-2-storm.webp" alt="Storm city stage gameplay"></td>
  </tr>
  <tr>
    <td align="center"><b>Stage 1 · Forest</b></td>
    <td align="center"><b>Stage 2 · Storm</b></td>
  </tr>
  <tr>
    <td><img src="assets/gameplay/stage-3-swamp.webp" alt="Swamp stage gameplay"></td>
    <td><img src="assets/gameplay/stage-4-city.webp" alt="Day city stage gameplay"></td>
  </tr>
  <tr>
    <td align="center"><b>Stage 3 · Swamp</b></td>
    <td align="center"><b>Stage 4 · City</b></td>
  </tr>
  <tr>
    <td><img src="assets/gameplay/stage-5-space.webp" alt="Space stage gameplay"></td>
    <td><img src="assets/gameplay/stage-6-castle.webp" alt="Night castle stage gameplay"></td>
  </tr>
  <tr>
    <td align="center"><b>Stage 5 · Space</b></td>
    <td align="center"><b>Stage 6 · Night Castle</b></td>
  </tr>
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
  <tr>
    <td width="50%"><img src="assets/editor/city-overview.webp" alt="Cat vs Ghosts custom level editor showing a large city level"></td>
    <td width="50%"><img src="assets/editor/space-overview.webp" alt="Cat vs Ghosts custom level editor showing a large space level"></td>
  </tr>
  <tr>
    <td align="center"><b>City level overview</b></td>
    <td align="center"><b>Space level overview</b></td>
  </tr>
</table>

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

The game includes an automatic benchmark/calibration stage that measures rendering and logic workloads and stores a local performance profile. Performance work was tested on both modern hardware and an older laptop with hybrid Intel/NVIDIA graphics, where rendering and GPU-selection bottlenecks were investigated separately.

The Windows release was also verified on a laptop with an NVIDIA RTX 3060, confirming that the packaged game used the discrete GPU.

### Content pipeline

Objects are described through a registry instead of being hard-coded individually into level text. Brush metadata can include asset references, anchors, gameplay roles and performance-related information. This allowed the content set to grow while keeping authoring manageable.

### Release/debug separation

Profiling and diagnostic code is useful during development but should not ship as part of the public game. The PyInstaller build explicitly excludes development-only profiler modules while bundling the runtime assets and levels required by the release.

### Localization and player data

The game supports EN / PL / RU / UA through a keyed translation system with English fallback. Profiles, saves, campaign progression and settings are stored outside the packaged application so reinstalling or upgrading the game does not overwrite player data.

## High-level structure

```text
Game flow / menus
        |
        +-- Campaign & stage selection
        +-- Profiles / saves / settings
        +-- Localization
        |
Runtime core
        |
        +-- Player / enemies / bosses
        +-- Collision & entity logic
        +-- Rendering & backgrounds
        +-- Audio / input / screenshots
        |
Content tools
        |
        +-- Level editor
        +-- Object-layer registry
        +-- Brush / anchor workflow
        |
Release pipeline
        |
        +-- Performance calibration
        +-- PyInstaller build
        +-- Windows installer
```

## Portfolio scope

This repository demonstrates the finished project without publishing the complete proprietary implementation of the game or its level editor.

Public portfolio material may include screenshots, demonstrations, selected architecture notes and carefully chosen code excerpts where they do not expose the complete implementation.

## Current release

**Cat vs Ghosts 1.0.0** is the first completed Windows release line. The game has been tested as an installed desktop application on different hardware generations.

## Author

**Vitalii Butsanov**  
Python developer / personal software projects

GitHub: [vitaliibutsanov](https://github.com/vitaliibutsanov)

## License

Copyright © 2026 Vitalii Butsanov. All rights reserved.

This repository is a portfolio showcase. No permission is granted to copy, redistribute, modify, repackage, sell, or incorporate its original materials into another project except where explicitly permitted by applicable law or the repository license.
