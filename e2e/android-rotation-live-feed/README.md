# Android Rotation Live-Feed Fixture

> **TEST DATA ONLY - NOT FOR NAVIGATION**

This fixture is a minimal persisted Android live-feed cache containing an empty,
canonical NOTAM checkpoint. It was generated through Aerobag's `notam-state`
and `nav-kv-package` implementations and contains no operational FAA records.

The Android rotation E2E test copies `files/live-feeds` into the debug app's
private storage. Restoring it exercises immutable-resource discovery, canonical
NOTAM preparation, and one-shot prepared projection promotion without network
access.
