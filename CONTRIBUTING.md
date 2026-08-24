# Contributing

Mardwerk is early-stage. Open an issue in the affected repository before a
large change so scope and ownership are clear.

Keep pull requests narrow and complete:

1. Follow the repository's local instructions.
2. Start with one end-to-end vertical slice.
3. Add only the smallest checks that prove changed behavior.
4. Update documentation when a public contract changes.
5. Remove obsolete code and dependencies before requesting review.

Changes to generators must consume released `@mardwerk` packages. Shared
contracts belong in `mardwerk/foundation`, which is implemented and released
before dependent generator work begins.
