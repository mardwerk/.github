# Mardwerk

Mardwerk builds open-source foundations and generators for deterministic game
content.

## Build order

```text
mardwerk/foundation
        ↓
released @mardwerk packages
        ↓
unit-generator and map-generator in parallel
```

[`foundation`](https://github.com/mardwerk/foundation) owns the shared manifest,
generator SDK, service/runtime adapters, model client, and Svelte UI. Generators
consume released packages instead of copying foundation code.

## Direction

- Node.js 24, TypeScript, and Fastify on the backend
- Svelte 5 and SvelteKit for generator interfaces
- Separate referenced artifacts inside a universal bundle envelope
- Local-first execution with a clear path from SQLite and local files to
  PostgreSQL, NATS JetStream, and S3-compatible storage
- Apache-2.0 for the foundation; MPL-2.0 for complete generator applications

Mardwerk is at an early stage. The foundation comes first; the unit and map
generators follow once its packages are released.
