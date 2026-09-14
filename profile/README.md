# Mardwerk

Mardwerk builds independently usable generators and local tools for game content, alongside a proprietary production platform. Explicit inputs and retained evidence support reproducible operations where their contracts establish it; external model generation is not inherently deterministic.

The [meta repository](https://github.com/mardwerk/.github) owns the [shared vocabulary](https://github.com/mardwerk/.github/blob/main/CONTEXT.md), [technical direction](https://github.com/mardwerk/.github/blob/main/ROADMAP.md) and [licensing policy](https://github.com/mardwerk/.github/blob/main/LICENSING.md). Product repositories add their own domain contracts.

| Repository | Role |
| --- | --- |
| [Unit Generator](https://github.com/mardwerk/unit-generator) | MIT unit generation engine and CLI, with UnitLab as its local human interface. |
| [Map Generator](https://github.com/mardwerk/map-generator) | MIT spatial engine and CLI, plus GPL-3.0-only MapLab in one repository. The selected desktop uses PySide6/Qt Widgets and Qt Quick 3D. |
| [Foundation](https://github.com/mardwerk/foundation) | Optional existing Apache-2.0 artifact helpers, model transport and web controls. A package dependency is not required to share vocabulary. |
| Reference Corpus, private | Captured references, provenance, qualified snapshots and explicit exports. |
| [Towerright](https://github.com/mardwerk/towerright), private | Proprietary cross-generator production, retained revisions, review and service coordination. |

Map Generator currently admits a bounded 2D research workflow. The approved native Lab, terrain generation and consecutive maps from one World are being developed against explicit qualification steps. Local graphics and compute trials inform the MVP; they do not establish a completed world generator.

The Labs and Towerright call generators independently. Essential generation remains in the public engines. The future 3D production product and consuming games retain separate contracts; listing or transferring a legacy repository does not change its license.

Foundation grows only from demonstrated shared needs. Current consumers still use its manifest and Svelte UI; legacy service/SDK code is not the required architecture for every product. Node/Svelte web applications and the Qt desktop can coexist without a universal UI or orchestration framework.
