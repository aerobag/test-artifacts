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
