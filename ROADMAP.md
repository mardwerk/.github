# Technical direction

This records the current v0.1 constraints. It is a direction, not a promise of
dates or a substitute for repository-level design decisions.

## Delivery order

1. Establish the v0 foundation and reference corpus. These initial versions
   exist; the corpus is still provisional.
2. Complete the full `unit-generator`. Research for `map-generator` runs in
   parallel.
3. Once the unit generator is complete, review its implementation for reusable
   code and migrate the shared parts into `foundation`. Use the completed
   UnitSpec to finalize the reference corpus's unit data and contracts.
4. Develop `map-generator` as its research resolves the implementation
   direction. This work can proceed in parallel with the foundation migration
   and corpus finalization, depending on research readiness.

Foundation grows from concrete generator needs. Its initial package release
is no longer a prerequisite for generator development; local package links
support the current work, with releases carrying shared changes to consumers.

## Repository responsibilities

- `foundation` owns shared contracts and infrastructure. After the unit
  generator is complete, it receives the parts identified as reusable.
- `unit-generator` owns UnitSpec and the full unit generation application.
  Unit-specific behavior stays here when shared code moves into foundation.
- `reference-corpus` owns private reference-data tooling and snapshots. Its v0
  contracts are provisional; UnitSpec guides unit corpus finalization, while
  map research informs map-specific requirements. Public generators consume
  exports without depending on the private repository at runtime or in CI.
- `map-generator` owns map research and the resulting map generation
  application. Research determines its implementation direction and timing.

Foundation provides:

- `@mardwerk/manifest`
- `@mardwerk/generator-sdk`
- `@mardwerk/service-kit`
- `@mardwerk/model-client`
- `@mardwerk/ui`
- `apps/ui-lab`
- `examples/reference-generator`

The manifest is a generic bundle envelope. Units, maps, models, textures, rigs,
animations, previews, and reports remain separate referenced artifacts.

## v0.1 stack

- Node.js 24 LTS, TypeScript, and Fastify
- `fnm` for Node version management, with `.node-version` committed per repository
- Svelte 5 and SvelteKit
- Bits UI only behind the public `@mardwerk/ui` package
- Plain CSS and CSS custom properties
- Server-side `node:sqlite`
- Inline jobs for tests, CLI use, and the smallest local mode
- NATS JetStream durable pull consumers with explicit acknowledgements for
  distributed API/worker execution

Tailwind, Storybook, Python, Rust, Mojo, Kubernetes, Helm, and KEDA are outside
v0.1. A native compute language is introduced only after profiling identifies
a bottleneck.

## Deployment boundary

```text
Single host:   SQLite + local artifacts
Multiple hosts: PostgreSQL + S3-compatible artifacts + NATS JetStream
```

Future deployment maps stateless web/API and independently scaled workers to
Kubernetes, uses KEDA with JetStream lag for autoscaling, and packages the
system with Helm. v0.1 documents these boundaries but does not implement them.

## Open-source boundary

- Foundation: Apache-2.0
- Unit Generator: MPL-2.0, including complete single-unit generation, upgrade
  graphs, validation, bounded repair, local UI/API/CLI/worker, and artifacts
- Map Generator: MPL-2.0, including continuous worlds, connectivity and
  traversal, terrain, scoring, bounded repair, local UI/API/CLI/worker,
  previews, and artifacts

Future hosted or proprietary products may add orchestration, cross-generator
analysis, expensive ranking, production asset libraries, integrations, and
collaboration. Essential generation remains open source.

## Testing

Test contracts and critical flows, not coverage targets. Use deterministic
fixtures, bounded-repair checks, API/worker lifecycle tests, and one browser
happy path per generator. Avoid live model calls in CI, broad snapshot suites,
test-per-field patterns, and exhaustive malformed-input matrices.
