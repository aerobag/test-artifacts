# Obstacle Delta Trace

This fixture contains historical obstacle package snapshots derived from the
FAA Daily Digital Obstacle File. The packages are intentionally stored as the
rendered obstacle ZIPs that existed at capture time; tests reconstruct a
canonical `obstacles_by_id` state from the full-detail z12 obstacle tiles.

The trace covers daily production snapshots from 2026-04-13 through
2026-04-24. Delta tests use the full sequence to exercise unchanged, changed,
added, and removed obstacle records across real-world updates.
