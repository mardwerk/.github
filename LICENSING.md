# Ecosystem licensing

Mardwerk's generators expose independently usable local computation. Towerright supplies an independently developed proprietary production platform. A local Lab and its generator may share a repository without sharing the same license.

| Repository / scope | Selected license and ownership |
| --- | --- |
| Map Generator library, CLI, validation and execution contracts | MIT; independent of MapLab and Towerright |
| MapLab in Map Generator, including the original Qt harness code | GPL-3.0-only, using Qt Widgets and Qt Quick 3D; see the repository's [scope policy](https://github.com/mardwerk/map-generator/blob/main/LICENSING.md) |
| Unit Generator original engine, CLI and current UnitLab | MIT; its dependencies retain their own licenses |
| Existing Foundation packages | Apache-2.0, preserved with their notices; optional reuse does not require relabeling existing packages MIT |
| Towerright original platform and private production documentation | Proprietary; independent of the Lab, calling generators through explicit contracts |
| Reference Corpus and reference snapshots | Private repository/content with source-specific rights; no blanket public grant is made here |
| Future 3D production product and legacy game repositories | Their existing licenses remain in force until individually reviewed. Moving a repository or naming it in this ecosystem does not relicense its contents. |

The Map Generator repository has licenses assigned by component. “Dual license” must not be interpreted as `MIT OR GPL-3.0-only` for every file. A distributed application containing Qt Quick 3D follows its applicable GPL obligations; the independent engine retains its MIT grant. The platform's language and private implementation do not derive from the local application's toolkit.

MIT allows commercial use, modification and proprietary reuse subject to its notice requirements. Describe the public tools as local or standalone editions, not as noncommercial-only editions. Generation results, supplied assets and captured references have their own content provenance; a software license is not a blanket grant over those materials.

In this meta repository, [LICENSE](LICENSE) grants MIT for original documentation except where a specific notice applies. [CONTEXT.md](CONTEXT.md) was moved from Foundation and retains Apache-2.0; its full text is in [LICENSES/Apache-2.0.txt](LICENSES/Apache-2.0.txt), with origin/change notices in [NOTICE](NOTICE). Brand assets and third-party content are excluded from the documentation grant. No trademark rights are granted.
