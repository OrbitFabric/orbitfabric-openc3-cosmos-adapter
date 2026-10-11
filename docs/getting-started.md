# Getting Started

## Install the current published release

Core [v1.4.0](https://github.com/OrbitFabric/orbitfabric/releases/tag/v1.4.0), GitHub Release Source [v0.1.0](https://github.com/OrbitFabric/orbitfabric-github-release-source/releases/tag/v0.1.0) and this adapter [v0.2.1](https://github.com/OrbitFabric/orbitfabric-openc3-cosmos-adapter/releases/tag/v0.2.1) were published on 2026-09-25. The adapter's exact Release Descriptor digest is indexed in the canonical Catalog. Product publication does not promote Core-owned adapter lifecycle or integration contracts from candidate maturity; no PyPI publication is assumed.

The current Catalog-based consumer path is:

```bash
python3 -m venv .venv
. .venv/bin/activate
python -m pip install -r https://github.com/OrbitFabric/orbitfabric/releases/download/v1.4.0/orbitfabric-install.txt
orbitfabric adapter install openc3-cosmos --version 0.2.1
orbitfabric adapter list
orbitfabric adapter verify <instance-id>
```

The installed identity is `github.com/OrbitFabric:orbitfabric/openc3-cosmos@0.2.1`. No repository clone, manual adapter download or Project Lock is required for this Catalog/provider path. Use `--catalog-revision <40-character-commit-sha>` to pin the Catalog, or `--catalog ./catalog.json` for a local snapshot. Obtain the matching `v0.2.1` source archive only when example files or runner scripts are needed. Publication alone does not establish a separate post-publication external greenfield acceptance for this coordinated version.

## Historical manual installation reference

The explicit-source walkthrough below preserves the historical `v0.1.0` baseline and its original FAROTECH Source Coordinate. It is not the current `v0.2.1` Catalog-based onboarding path. Historical release bytes and accepted evidence remain unchanged.

This page describes the **consumer** path.

The normal OrbitFabric user installs a released adapter through Adapter Manager and executes it through Core. Editable source installs and the direct adapter CLI belong to the contributor workflow documented in [Development](development.md).

> **Historical v0.1.0 walkthrough:** `v0.1.0` remains published and immutable. The steps below use its explicit-source wheel and exact historical Core pin. Current consumers should follow the `v0.2.1` published installation above; `v0.2.0` remains available as an exact published intermediate release.

## Historical explicit-source installation and execution

The following numbered steps preserve the `v0.1.0` accepted reference lane; use the matching historical wheel, tag and example inputs for reproducibility. They are not interchangeable with current `v0.2.1` assets.

## 1. Install OrbitFabric Core

Install a compatible OrbitFabric Core environment first.

The current adapter baseline is validated against exact Core commit:

```text
b4e1185de4931ff125be699dfe09f63ab3746015
```

## 2. Obtain adapter release assets

The stable release membership is:

```text
orbitfabric_openc3_cosmos_adapter-0.1.0-py3-none-any.whl
adapter-release.json
SHA256SUMS
```

The Release Descriptor defines publisher-owned release identity. The wheel is the managed installation artifact.

## 3. Install through Adapter Manager

Verify the descriptor digest and install the exact wheel:

```bash
DESCRIPTOR_SHA256="$(sha256sum adapter-release.json | awk '{print $1}')"

orbitfabric adapter install adapter-release.json \
  --artifact orbitfabric_openc3_cosmos_adapter-0.1.0-py3-none-any.whl \
  --descriptor-sha256 "$DESCRIPTOR_SHA256" \
  --json > install.json
```

Capture the returned adapter instance id and verify the managed installation:

```bash
ORBITFABRIC_ADAPTER_INSTANCE_ID="$(python - <<'PY'
import json
print(json.load(open('install.json'))['instance_id'])
PY
)"

orbitfabric adapter verify "$ORBITFABRIC_ADAPTER_INSTANCE_ID" --json
```

A normal consumer does not need `pip install -e`, the adapter source package or the direct `orbitfabric-openc3-cosmos` command.

## 4. Run the product example

The repository contains one focused consumer-facing example:

```bash
bash examples/01-scenario-verification-projection/run.sh \
  "$ORBITFABRIC_ADAPTER_INSTANCE_ID"
```

The runner:

```text
exports a Core Integration Input Set from the example Mission Model
    -> verifies the installed adapter instance
    -> executes verification_projection through Adapter Manager
    -> writes disposable projection output
```

See [Product Example](examples.md) for the expected artifacts and evidence boundary.

## 5. Use your own inputs

The public operation is:

```text
verification_projection
    required operation input: scenario
```

Execute it through Core:

```bash
orbitfabric adapter execute "$ORBITFABRIC_ADAPTER_INSTANCE_ID" \
  --operation verification_projection \
  --input-set-manifest <integration_input_manifest.json> \
  --profile <projection-profile.yaml> \
  --operation-input "scenario=<scenario.yaml>" \
  --output-dir <output-directory>
```

Representative outputs:

```text
integration_result.json
verification_projection/verification_projection_plan.json
verification_projection/cosmos/verification.py
verification_projection/cosmos/verification_suite.py
```

The generated Python files are COSMOS-facing target artifacts. The Integration Result remains the primary OrbitFabric execution evidence surface.

## Next

- [Product Example](examples.md)
- [Projection Profile and Bindings](projection-profile-and-bindings.md)
- [Integration Coverage](integration-coverage.md)
- [Runtime Dependencies](runtime-dependencies.md)
