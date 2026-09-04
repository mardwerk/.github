# Mardwerk

Mardwerk builds open-source foundations and generators for deterministic game
content.

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

[`map-generator`](https://github.com/mardwerk/map-generator) is currently in
research. That research determines the map application's design and when
implementation can proceed.

## Direction

- Node.js 24, TypeScript, and Fastify on the backend
- Svelte 5 and SvelteKit for generator interfaces
- Separate referenced artifacts inside a universal bundle envelope
- Local-first execution with a clear path from SQLite and local files to
  PostgreSQL, NATS JetStream, and S3-compatible storage
- Apache-2.0 for the foundation; MPL-2.0 for complete generator applications

The detailed technical direction lives in
[ROADMAP.md](https://github.com/mardwerk/.github/blob/main/ROADMAP.md).
