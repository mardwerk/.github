# Mardwerk

Mardwerk builds open-source foundations and generators for game content.
Explicit inputs and retained evidence support reproducible operations where
their contracts establish it; external model generation is not inherently deterministic.

## Build order

| Stage | Unit generator, foundation, and reference corpus | Map generator |
| --- | --- | --- |
| Starting point | v0 foundation and provisional reference corpus created | |
| Current work | Build the full unit generator | Research in parallel |
| After unit completion | Move reusable code into foundation; use UnitSpec to finalize the unit reference corpus | Develop in parallel as research resolves the direction |

Map development depends on research readiness and can overlap the foundation
migration and corpus finalization.

## Repositories

[`foundation`](https://github.com/mardwerk/foundation) owns the shared manifest,
generator SDK, service/runtime adapters, model client, and Svelte UI. It will
receive reusable code identified after the unit generator is complete.
Generators use its packages through local links during development and
versioned releases as they become available.

[`unit-generator`](https://github.com/mardwerk/unit-generator) owns UnitSpec and
the full unit generation application. Its completed specification will guide
finalization of the private reference corpus's unit data and contracts.

The private `reference-corpus` repository owns reference-data tooling and
snapshots. Generators consume its exports without requiring the private
repository at runtime or in CI.

[`map-generator`](https://github.com/mardwerk/map-generator) contains the spatial
engine and Map Lab, its primary human workbench. The admitted research CLI
handles a bounded 2D grid. The selected next application is a Linux-native
PySide6/Qt Widgets Lab; terrain and multi-map capabilities require their own
implementation and acceptance evidence.

The private [`towerright`](https://github.com/mardwerk/towerright) repository
records continuing production, accepted revisions and cross-generator assembly.
It is separate from each generator’s explicit-input computation.

## Direction

- Node.js 24, TypeScript, and Fastify for the existing Node applications
- Svelte 5 and SvelteKit for web interfaces; Python/PySide6 with Qt Widgets for native Map Lab
- Separate referenced artifacts inside a universal bundle envelope
- Local execution from explicit inputs; optional persistent-service infrastructure
  where a concrete consumer requires it
- Apache-2.0 for the foundation; MPL-2.0 for complete generator applications

The detailed technical direction lives in
[ROADMAP.md](https://github.com/mardwerk/.github/blob/main/ROADMAP.md).
