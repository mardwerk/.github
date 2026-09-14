# Mardwerk shared language

<!-- SPDX-License-Identifier: Apache-2.0; moved from mardwerk/foundation/CONTEXT.md on 2026-09-13, with terminology-location updates. -->

This is the canonical shared glossary for the Mardwerk ecosystem. Product glossaries add domain-specific terms; sharing language does not require sharing a runtime or serialized schema.

## Language

### Products and tools

**Unit Generator CLI**:
The canonical product and complete execution/generation engine for game units under a selected Definition. Its explicit command and result contracts are usable by humans, agents and other products.
_Avoid_: UnitLab when referring to generation execution

**Map Generator CLI**:
The canonical product and complete execution/generation engine for worlds and playable maps under a selected Definition.
_Avoid_: MapLab when referring to generation execution

**UnitLab**:
The local human abstraction over the Unit Generator CLI. UnitLab may provide a localhost web UI for ordinary users and a separate diagnostic workbench for developers; neither is the canonical generation engine.
_Avoid_: Unit Generator CLI when referring to the human interface, Unit Lab as the CLI

**MapLab**:
The local human abstraction over the Map Generator CLI. MapLab may provide a native application workbench for authoring world and map inputs, configuring and invoking the CLI, and inspecting results.
_Avoid_: Map Generator CLI when referring to the human interface

**Diagnostic workbench**:
A developer-facing interface for inspecting requests, provider calls, lifecycle events, evidence, validation, qualification and artifacts. It exposes more operational detail than the ordinary Lab experience and does not become a second generator.
_Avoid_: Human abstraction, production acceptance, quality score

**Agent caller**:
An automated caller that invokes a canonical generator CLI directly with explicit inputs and receives its result and evidence.
_Avoid_: Agent UI, hidden orchestration

**Towerright caller**:
Towerright's direct use of a generator CLI or explicit result files. Towerright retains production state and decisions; it does not depend on a Lab UI.
_Avoid_: Lab integration, generator-owned production state

**Reference Corpus**:
Captured, versioned reference data with provenance and declared limitations, used by generation and evaluation work.
_Avoid_: Reference Lab, gold standard for the entire corpus

### Generation and assessment

**Definition**:
The contract that specifies a generation task's input, output and rules.
_Avoid_: Prompt when referring to the whole contract

**Candidate**:
A proposed version of generated or edited content, which may be accepted, rejected or still unchecked under the selected Definition.
_Avoid_: Valid result before its required checks pass

**Result**:
The recorded outcome of a generation attempt, including any returned content and evidence. A Result can describe success, failure or cancellation.
_Avoid_: Candidate when referring to the whole outcome, success as an implication of Result

**Validation**:
A determination of conformance to declared rules and constraints. Passing Validation establishes only the checks performed, not source fidelity, balance or enjoyment.
_Avoid_: Quality evaluation, balance proof

**Evaluation**:
An assessment of content against a stated question and context, using measurements, comparisons or human judgments.
_Avoid_: Validation when judging usefulness, fidelity or play experience

**Metric**:
A defined measurement of content or behavior, with a stated scope and interpretation. A value alone does not establish that larger or smaller is better.
_Avoid_: Quality score for a raw measurement

**Diagnostic finding**:
An observation about a rule violation, suspicious pattern or missing evidence, supported by the applicable checks or measurements. A collection of findings is not an overall quality rating.
_Avoid_: Quality score, objective quality

**Simulation**:
A modeled execution of game behavior in a specified scenario. Its observations describe that model and scenario, not every consuming game or play situation.
_Avoid_: Playtest, balance proof

**Calibration**:
The adjustment of a measurement interpretation, threshold or scoring method against declared reference evidence. Its support is limited to the evidence and question used.
_Avoid_: Validation, proof of general quality

**Synthetic calibration**:
Calibration against authored or systematically altered examples. It is development evidence, not independent confirmation on unseen real content.
_Avoid_: Real-world calibration, validated quality

**Source fidelity**:
The degree to which an adaptation preserves the evidenced identity, defining traits and limitations of its source within the selected continuity. Deliberate adaptations and unsupported claims remain distinct from source facts.
_Avoid_: Canonical correctness inferred from a source name, name matching

**Gameplay quality**:
The suitability of a design's play experience for a stated audience and gameplay purpose. Mechanical conformance and uncalibrated heuristics do not establish it.
_Avoid_: Diagnostic index, validated design as an automatic quality judgment

**Competitive balance**:
The relative costs, benefits and strategic viability of content within a specified game, roster and player context.
_Avoid_: Neutral-scenario performance, universal balance

**Coverage**:
The extent of available evidence or supported behavior relative to an explicitly named scope. Missing or unsupported coverage is not a measured zero.
_Avoid_: Completeness without a scope, quality

### Reference evidence

**Reference snapshot**:
An identified version of captured reference material and its associated provenance, coverage and qualifications. A snapshot's identity does not establish complete or correct gameplay semantics.
_Avoid_: Current truth, validated benchmark by default

**Reference set**:
A declared selection of reference examples for a particular generation or evaluation purpose.
_Avoid_: Reference Corpus when referring to one selected set

**Reference family**:
A group of related examples whose shared origin, variants or derivations matter to the independence of an evaluation. Family membership depends on the claim being assessed.
_Avoid_: Independent samples for related variants

**Benchmark**:
A specified comparison of candidates or methods against reference cases and expected observations. Its conclusions depend on the cases, evaluation question and exposure history.
_Avoid_: Quality proof, calibration when no fitting occurs

**Reference qualification**:
A scoped judgment about a reference's completeness, compatibility or suitability as evidence. It is separate from the purpose for which the reference is used.
_Avoid_: Partition, official provenance as automatic qualification

**Design reference**:
An example of intended game content and behavior used to guide or assess an adaptation. Design approval is separate from source qualification, executable validity and balance evidence.
_Avoid_: Executable reference or gold benchmark solely because a design was approved

### Reference use and exposure

**Reference partition**:
A declared assignment of reference examples to a purpose within an evaluation protocol. Partition names express intended use; actual exposure determines which independence claims remain justified.
_Avoid_: Quality tier, split without a stated purpose

**Development partition**:
References available for authoring, debugging, prompt examples and exploratory evaluation, including synthetic calibration.
_Avoid_: Holdout, independent confirmation

**Calibration partition**:
References designated for fitting or tuning an evaluation method or its interpretation. They are development evidence for the fitted method, not its unseen confirmation.
_Avoid_: Holdout, gold quality tier

**Evaluation partition**:
References designated for assessing a stated procedure. Evaluation use alone does not imply that developers or tuners have remained unexposed to its contents or findings.
_Avoid_: Holdout unless its isolation conditions hold

**Holdout partition**:
References reserved from informative exposure during the development, tuning and selection relevant to a claim. Exposure that influences those decisions ends their unseen status for that claim, even if the stored label remains unchanged.
_Avoid_: Development examples, calibration data, held-out examples reused in prompts
