# Adapter Identity

Current published release: [`v0.2.1`](https://github.com/OrbitFabric/orbitfabric-openc3-cosmos-adapter/releases/tag/v0.2.1) (2026-09-25). See [release notes](releases/0.2.1.md). The historical `v0.1.0` release retains its FAROTECH Source Coordinate; `v0.2.0` remains the first published OrbitFabric-identity release.

The current source identity is:

```text
repository       orbitfabric-openc3-cosmos-adapter
distribution     orbitfabric-openc3-cosmos-adapter
python package   orbitfabric_openc3_cosmos_adapter
console command  orbitfabric-openc3-cosmos
adapter.id       orbitfabric-openc3-cosmos
integration.id   orbitfabric-openc3-cosmos
logical key      orbitfabric/openc3-cosmos
version          0.2.1
```

The logical adapter key is unchanged by the GitHub ownership migration.

## Release Source Coordinate lineage

Historical first stable release:

```text
v0.1.0
authority = github.com/FAROTECH
publisher = orbitfabric
name      = openc3-cosmos
```

Rendered:

```text
github.com/FAROTECH:orbitfabric/openc3-cosmos
```

First post-migration release:

```text
v0.2.0
authority = github.com/OrbitFabric
publisher = orbitfabric
name      = openc3-cosmos
```

Rendered:

```text
github.com/OrbitFabric:orbitfabric/openc3-cosmos
```

The historical v0.1.0 Source Coordinate remains immutable. The v0.2.0 coordinate records the new physical publication authority while retaining the same logical adapter key.

The source version and Source Coordinate do not by themselves constitute a published release. Release identity is completed only by the exact accepted source, tag, immutable release assets and their verified byte identities.

## Current published release

`v0.2.1` uses `github.com/OrbitFabric:orbitfabric/openc3-cosmos@0.2.1` and is indexed by exact version and Release Descriptor digest in the canonical Adapter Catalog. Product publication is distinct from the candidate maturity of generic Core lifecycle/integration contracts and the `orbitfabric.scenario_projection_accounting` `0.1-candidate` contract. The original `v0.1.0` and `v0.2.0` published bytes and Source Coordinates remain unchanged.
