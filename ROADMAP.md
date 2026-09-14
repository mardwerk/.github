# Technical direction

Updated 2026-09-13. This records selected responsibilities and the next work, not delivered capabilities or a schedule. Repository designs own their actual interfaces and evidence. The [shared glossary](CONTEXT.md) and [licensing policy](LICENSING.md) live here in the organization meta repository.

## Delivery direction

Develop the independently usable generators and their local human tools around explicit inputs and inspectable results. Map Generator's next application is the approved Qt workbench: PySide6/Qt Widgets plus Qt Quick 3D, separate generation workers, bounded terrain display and source-linked inspection. Its current admitted implementation is still a bounded 2D research CLI; local desktop experiments are not a completed terrain MVP.

Unit Generator evolves its own Definition and generation contracts. Reference Corpus supplies qualified exports and provenance without becoming a private runtime or CI prerequisite for public generators. Work can proceed in parallel as each product's evidence and dependencies permit.

Foundation remains one optional package workspace. Retain shared behavior because current callers need it; do not automatically migrate code there after a generator is complete. Its existing manifest and web UI have sibling consumers, and Unit Generator setup still builds model-client. SDK/service-kit remain legacy optional modules. Their source and examples are retained while default adoption and routine release expectations are removed. See [Foundation scope](https://github.com/mardwerk/foundation/blob/main/docs/scope.md).

## Repository responsibilities

| Repository | Ownership |
| --- | --- |
| `.github` meta | Canonical shared vocabulary, repository discovery, cross-product direction, licensing policy, public profile and brand references. No shared application runtime. |
| `foundation` | Optional artifact envelope/verification, model transport and Svelte controls with demonstrated consumers. Legacy HTTP job/runtime modules do not define product lifecycles. |
| `unit-generator` | MIT unit engine, CLI, Definitions, validation and current UnitLab. Unit-specific mechanics stay here. |
| `map-generator` | MIT spatial engine, CLI and independent contracts, plus GPL-3.0-only MapLab in the same repository. World/Map generation and validation remain engine responsibilities as implemented. |
| `reference-corpus` | Private capture, snapshots, qualification and domain exports with source-specific rights. |
| `towerright` | Proprietary continuing Series production, accepted World/asset revisions, cross-generator workflows, scheduling and future service operation. Calls engines independently of Labs. |
| Future 3D product and game consumers | Separate producer/consumer contracts and subprojects. Existing legacy repositories retain their current terms and scope until transfer/refactoring is separately executed. |

Domain glossaries remain in their product repositories. A common word does not require one serialized schema or runtime. The generic Foundation manifest is optional and does not silently replace Map Generator's existing research publication format. Maps, units, models, textures, rigs, animations, previews and findings retain producer-specific meaning.

## Application stacks

The existing Node applications use Node.js 24, TypeScript, Fastify where needed, Svelte 5/SvelteKit and ordinary CSS. Native MapLab selects Python/PySide6, Qt Widgets and Qt Quick 3D. The generator's compute implementation can evolve independently when a measured bottleneck justifies it. Rust/wgpu remains retained experimental evidence, not a second MapLab application to maintain. Neither the desktop toolkit nor its language dictates Towerright's platform stack.

SQLite/local artifacts and NATS/JetStream adapters exist in Foundation's legacy service example. They are not an ecosystem-wide execution requirement. Towerright should choose persistence, queues, hosting and scaling after proving its first actual production workflow; Kubernetes, Helm and KEDA are not prerequisites for local generation or the Lab MVP.

## Licensing and dependency direction

MIT engines and execution contracts are reusable independently. MapLab accepts GPL-3.0-only application distribution so the MVP can use the qualified Qt workbench. Its local workspace, run/cancel and inspection behavior stay in the application; generation rules must not acquire a Qt or GPL-only Lab dependency. Towerright remains a separate proprietary caller of the engines.

Unit Generator's original code is MIT. Existing Foundation packages remain Apache-2.0 with their notices. Reference content and generated/supplied assets retain their own terms. Future 3D/game repository transfers do not enact relicensing. The [scope policy](LICENSING.md) supersedes older MPL generator roadmaps and records the meta glossary's retained Apache provenance.

## Verification

Test contracts and critical flows with bounded deterministic fixtures where appropriate. Qualify actual generation outcomes separately from source fidelity, gameplay quality and external-model reproducibility. Native MapLab needs process lifecycle, source correspondence, real materials, chunk/LOD behavior and real Wayland interaction evidence; a browser happy path or bare terrain benchmark does not establish the finished application. Keep source, display, collision and navigation authority distinct.
