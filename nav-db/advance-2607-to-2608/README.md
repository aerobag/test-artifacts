# NAVDB Advance 2607 To 2608

Immutable production NAV19 inputs for testing transactional
runtime NAVDB advance.

Source publication identity:

```text
fixture-build
```

`source/` preserves the original publication index, selected cycle bundle
manifests, and NAVDB ZIP bytes. The index references products that are not
copied into this fixture; it records provenance and is not a minimal server
root.

Tests verify every copied artifact against `fixture.json`, then generate
deterministic publication views with controlled effective times.
