# NMS NOTAM API Trace

> **TEST DATA ONLY - NOT FOR NAVIGATION**
>
> This is a historical test capture, not current operational information or an
> official FAA product.

This fixture contains raw FAA NOTAM Management Service data captured from the
staging distribution API:

- compressed DOMESTIC and FDC Initial Load responses;
- 498 recorded poll boundaries;
- 580 unique raw AIXM updates first observed by those polls;
- fixed expectations for the resulting publication transition chain.

The poll trace retains recorded start, query, and completion times so collector
expiry behavior is deterministic. Source receive counts include overlap
duplicates; the payload list contains each content hash once because the
collector's durable contract deduplicates by payload hash.

Generate a replacement with the `nms-notams-fetch capture-fixture` command in
the Aerobag source repository. The capture command reads collector state
read-only, validates hashes, omits credentials and endpoints, and publishes
atomically to a new output directory.

The raw response bytes are intentionally unmodified because identifiers,
references, timestamps, and free text are production parser inputs. The
versioned manifest carries the same usage notice. See the repository
[provenance audit](../../PROVENANCE.md).

## Publication expectation revision (2026-09-11)

The raw capture, timestamps, and format are unchanged. `expected.json` now
reflects Aerobag's structured-airport projection introduced by
`f944d8886eb01df76f94afc608cfebbaebc4e061`, replacing the earlier keyword filter.
An exact-input comparison of its parent `64976c3d` and `4162491b` preserved all
96 old transition boundaries and all 820 old mutations. The 22 additional
boundaries represent two airport-linked AIRSPACE upserts, one explicit source
cancellation, and 27 expirations in 19 batches. Their 30 mutations cover AIRSPACE
(22), NAV (3), OBST (4), and SVC (1). The complete new trace has 118 transitions,
1,407 mutations, 1,178 removals, and 89 repeatedly mutated IDs.

Both full and incremental publication paths agree exactly. Expectations were
updated after tracing these differences, not by relaxing counts or hashes.
The source repository records the detailed comparison in
[`docs/testing/notam-projection-audit-2026-09-11.md`](https://github.com/aerobag/aerobag/blob/main/docs/testing/notam-projection-audit-2026-09-11.md).
