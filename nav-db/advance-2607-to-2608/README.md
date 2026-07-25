# NAVDB Advance 2607 To 2608

Immutable production NAV12 inputs for testing transactional runtime NAVDB
advance.

Source publication identity:

```text
master-ec68e4e91ce5 / 20260718T234628Z
```

`source/` preserves the original publication index, cycle bundle manifests,
and NAVDB ZIP bytes. The original publication index references products that
are not copied into this fixture; it records provenance and is not itself a
minimal test server root.

Tests should verify hashes from `fixture.json`. The Aerobag implementation will
generate deterministic `publication-2607` and `publication-2608` views from
these immutable source files. Those views will force the active cycle and test
clock rather than depend on the wall clock.

The positive E2E scenario must qualify a rich route and approach against both
NAVDBs before freezing it into the fixture. The initial candidate is `KRNT KPAE`
with `KPAE VOR-A ECEPO`.
