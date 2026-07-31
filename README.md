# Aerobag Test Artifacts

> **TEST DATA ONLY - NOT FOR NAVIGATION**
>
> These immutable historical fixtures are not current operational data and
> must not be represented as official FAA or NOAA products.

Large, real-world fixtures live here instead of the Aerobag source repository.
Set `AEROBAG_TEST_ARTIFACTS_ROOT` to this checkout before running the
artifact-backed test tier.

## Inventory

| Path | Contents |
| --- | --- |
| `metars/delta-three-hour/` | Three hours of generated METAR, TAF, and PIREP products |
| `nav-db/advance-2607-to-2608/` | NAV16 packages for transactional cycle advance |
| `nexrad/source-grid-three-hour/` | Three hours of raw NOAA MRMS NEXRAD grids |
| `notams/nms-api-trace/` | Raw FAA NMS Initial Load and incremental API trace |
| `obstacles/delta-trace/` | Daily FAA DOF-derived obstacle products |
| `winds-aloft/cycle-trace/` | NOAA/NCEP GFS filtered GRIB2 products |

Each fixture is immutable. Manifests and tests verify byte counts and SHA-256
hashes where applicable.

## Publication Audit

The repository passed archive-integrity, Git object-size, path, and credential
scans on 2026-07-25. No Git object exceeds GitHub's 100 MiB per-file limit and
no credential-like value was found.

The FAA NMS onboarding material reviewed by Aerobag contains no restriction on
redistributing FAA data. The unmodified NMS fixture is retained because its
real identifiers, references, timestamps, and text are part of the parser and
state-transition test coverage. See [PROVENANCE.md](PROVENANCE.md).

The artifacts are supplied without warranty and are never served through
Aerobag's live-feed publication path.
