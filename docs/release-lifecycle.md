# Release Lifecycle

Current published release: [`v0.2.1`](https://github.com/OrbitFabric/orbitfabric-openc3-cosmos-adapter/releases/tag/v0.2.1) (2026-09-25). Earlier releases `v0.1.0` and `v0.2.0` remain published with their original Source Coordinate identities.

The adapter preserves three separate product objects:

```text
Adapter Release Descriptor
    publisher-owned exact release identity and artifact membership

Adapter Project Lock
    consuming-project exact desired state

GitHub Release / source provider
    published bytes, transport and provider facts
```

Catalog selection and Adapter Manager lifecycle belong to OrbitFabric Core; this repository owns the adapter's COSMOS-specific projection and its release material.

## Published release lineage

| Version | Publication | Source Coordinate | Scope |
| --- | --- | --- | --- |
| [`v0.1.0`](https://github.com/OrbitFabric/orbitfabric-openc3-cosmos-adapter/releases/tag/v0.1.0) | 2026-09-03 | `github.com/FAROTECH:orbitfabric/openc3-cosmos@0.1.0` | Historical first stable release and separately accepted COSMOS native-runtime evidence |
| [`v0.2.0`](https://github.com/OrbitFabric/orbitfabric-openc3-cosmos-adapter/releases/tag/v0.2.0) | 2026-09-21 | `github.com/OrbitFabric:orbitfabric/openc3-cosmos@0.2.0` | Added generic Result-owned Scenario Projection Accounting |
| [`v0.2.1`](https://github.com/OrbitFabric/orbitfabric-openc3-cosmos-adapter/releases/tag/v0.2.1) | 2026-09-25 | `github.com/OrbitFabric:orbitfabric/openc3-cosmos@0.2.1` | Post-migration identity/metadata patch with no new projection behavior |

The first release's historical FAROTECH Source Coordinate is not rewritten. The generic `orbitfabric.scenario_projection_accounting` contract stays at `0.1-candidate` despite the published `v0.2.x` adapter products.

## Current release membership

Publisher-owned `v0.2.1` assets:

```text
orbitfabric_openc3_cosmos_adapter-0.2.1-py3-none-any.whl
adapter-release.json
SHA256SUMS
```

The `v0.2.1` tag is at source commit `b3120b5b1012d1dfdfcb14a6a4aba7716a41308e`. The canonical Adapter Catalog indexes its Release Descriptor SHA-256:

```text
a91e15655a9dfc9ffd7a42d3e94dbbd24be580c6a2bd58b87904e2f985346a97
```

The exact pinned OrbitFabric Core dependency for the adapter development and native conformance lane remains `b4e1185de4931ff125be699dfe09f63ab3746015`. Its transport switched from a Git URL to a commit-addressed HTTPS source archive, without changing the pin.

GitHub-generated source archives are transport conveniences, not publisher-owned Adapter Release Descriptor membership.

## Evidence boundaries

Hosted CI validates Python 3.11/3.12 checks, Core conformance, product behavior, exact COSMOS source/API compatibility, managed installation, release proof and the example consumer path.

External native COSMOS acceptance is separate: the pinned OpenC3 COSMOS v7.3.0 runtime, command/telemetry behavior, Script Runner and CTRF report are exercised through [Native COSMOS Acceptance](native-cosmos-acceptance.md). The accepted `v0.1.0` native evidence remains `v0.1.0` evidence; it is not a new `v0.2.1` post-publication greenfield replay.

For future releases, review the exact accepted source commit, all required CI/native gates, release tag, wheel and descriptor, published asset digests and any claimed independent external acceptance before considering the release closed. [Maintainer / Publisher Guide](publishing.md) documents the reusable preparation sequence.

## Current acquisition boundary

With published Core `v1.4.0` and GitHub Release Source `v0.1.0`, consumers can use exact Catalog-based acquisition of `v0.2.1` and verify the Adapter Manager installation. The historical explicit-source path remains available for reproducing the `v0.1.0` reference lane.

The Core-owned adapter lifecycle and integration contracts remain at candidate maturity. No broader OpenC3 COSMOS compatibility or production qualification is claimed.
