# Cat vs Ghosts

**Cat vs Ghosts** is a 2D desktop platformer developed as a long-form personal Python project. This repository is a public portfolio showcase of the finished game, its engineering decisions, and its custom development tools.

> **Status:** v1.0.0 — Windows desktop build completed and tested on both older hybrid-GPU hardware and a modern NVIDIA laptop.

## Overview

The project grew from a small platformer prototype into a complete game with its own campaign flow, profiles and saves, localization, editor tooling, performance calibration, Windows packaging, and a large object/brush content pipeline.

The production repository is kept **private**. This public repository intentionally contains portfolio material rather than the complete game and level-editor source code.

## Key features

- Multi-stage platforming campaign with distinct visual themes and bosses
- Custom level editor used to build and revise game content
- Object-layer / brush registry for reusable gameplay and decorative objects
- Player profiles, campaign progression, save/load flow, settings and screenshots
- Keyboard and mouse UI navigation with a **last-input-wins** interaction model
- Localization in **English, Polish, Russian and Ukrainian**
- Automatic runtime performance calibration for different hardware classes
- Performance-oriented rendering work, including optimized background pipelines
- Windows desktop packaging with **PyInstaller** and installer integration
- Development-only profiling tools excluded from the final packaged build

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

### Custom content tooling

A major part of the project is the in-game/editor-side content workflow. Objects are described through a registry instead of being hard-coded individually into level text. Brush metadata includes asset references, anchors, gameplay roles and performance-related information. This made it possible to grow the content set while keeping level creation manageable.

### Hardware-aware performance work

The game includes an automatic benchmark/calibration stage that measures rendering and logic workloads and stores a local performance profile. Performance work was tested on both modern hardware and an older laptop with hybrid Intel/NVIDIA graphics, where rendering and GPU-selection bottlenecks were investigated separately.

### Release/debug separation

Profiling and diagnostic code is useful during development but should not ship as part of the public game. The PyInstaller build explicitly excludes development-only profiler modules while bundling the runtime assets and levels needed by the release.

### Localization and user-facing systems

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

This repository is intended to demonstrate the project without publishing the complete proprietary implementation of the game or its level editor.

Planned public material includes:

- gameplay screenshots
- editor screenshots
- short gameplay/editor demonstrations
- selected architecture notes
- carefully chosen code excerpts where they do not expose the complete implementation
- Windows test-build information

## Current release

**Cat vs Ghosts 1.0.0** is the first completed Windows release line. The final build has been tested as an installed application, including discrete NVIDIA GPU usage on supported hardware.

## Author

**Vitalii Butsanov**  
Python developer / personal software projects

GitHub: [vitaliibutsanov](https://github.com/vitaliibutsanov)

## License

Copyright © 2026 Vitalii Butsanov. All rights reserved.

This repository is a portfolio showcase. No permission is granted to copy, redistribute, modify, repackage, sell, or incorporate its original materials into another project except where explicitly permitted by applicable law or the repository license.
