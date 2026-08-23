# Fixture Provenance

## Source Summary

| Fixture | Upstream source | Rights basis | Audit result |
| --- | --- | --- | --- |
| METAR/TAF/PIREP | NOAA/NWS Aviation Weather Center | NWS information is public domain unless noted otherwise | Clear |
| NAVDB | FAA Aeronautical Information Services data products; Natural Earth basemap data | U.S. government works and Natural Earth public domain | Clear |
| NEXRAD | NOAA/NCEP MRMS `CONUS_L2_CREF_QCD` | NOAA-produced data is public domain in the U.S. | Clear |
| NMS NOTAM | FAA NOTAM Management Service Initial Load and `lastUpdatedDate` API | U.S. government data; DOT policy supports redissemination; reviewed onboarding material contains no redistribution restriction | Clear |
| Obstacles | FAA Daily Digital Obstacle File | FAA states DOF is public domain with no use restrictions, but says not to alter and present it as source data | Clear as a derived, labeled fixture |
| Winds aloft | NOAA/NCEP GFS 0.25-degree data via NOMADS | NOAA-produced data is public domain in the U.S. | Clear |
| Release journeys | Derived compact FAA/NOAA/Natural Earth publication assembled by Aerobag | Same public-domain sources and Aerobag-created CC0 fixture metadata | Clear as labeled, non-navigation test data |

Aerobag-created fixture manifests, documentation, and packaging metadata are
dedicated under CC0-1.0. Aerobag does not claim copyright in U.S. government
source data.

The release-journey publication retains only the package members and historical
live-feed states needed to exercise representative UI capabilities. It is
derived test data, labeled for automated testing, and is not an official source
or a product for navigation.

## References

- [DOT Order 1351.34](https://www.transportation.gov/sites/dot.gov/files/docs/mission/128511/policy-data-management-s10-160926-001-d5-071317.pdf)
  says DOT should not impose restrictions on public reuse, resale, or
  redissemination of DOT data and notes that federal government works are in
  the public domain under 17 U.S.C. 105.
- [FAA NMS FAQ](https://www.faa.gov/about/initiatives/notam/faqs) says NMS
  produces digital NOTAM data for third-party vendors and preflight briefing
  providers.
- [FAA Aeronautical Data and Products](https://www.faa.gov/data/aero_data)
  identifies FAA Aeronautical Information Services as the producer of the
  aeronautical data used by the NAVDB fixture.
- [FAA DOF FAQ](https://www.faa.gov/air_traffic/flight_info/aeronav/obst_data/doffaqs/)
  states that DOF data is public domain and has no use restrictions, while
  warning users not to change the data.
- [NWS disclaimer](https://www.weather.gov/disclaimer/) states that NWS web
  information is public domain unless specifically noted and prohibits
  representing modified material as official government information.
- [NOAA/NCEI data licensing](https://www.ncei.noaa.gov/archive) states that
  federal environmental data is public domain in the United States.
- [Natural Earth terms](https://www.naturalearthdata.com/about/terms-of-use/)
  dedicate all Natural Earth raster and vector data to the public domain.

## NMS Review

The NMS fixture was captured from the staging distribution API from
2026-07-24T15:32:07Z through 2026-07-25T17:17:48Z. It contains:

- 26,864 DOMESTIC and 5,766 FDC Initial Load messages;
- 498 poll boundaries and 580 unique raw AIXM updates;
- no API URL, OAuth credential, token, client identifier, or local source path;
- no credential-like scanner findings;
- 46 occurrences of operational U.S. government email addresses in NOTAM text,
  all under `faa.gov`, `us.af.mil`, or `spaceforce.mil`.

Those addresses are part of publicly distributed operational notices rather
than Aerobag user data. The FAA onboarding correspondence and supplied
documentation reviewed by Aerobag contain no restriction on redistributing FAA
data. Public FAA material identifies NMS as a source for third-party vendors,
and DOT policy supports reuse and redissemination of federal data.

The fixture retains the exact FAA response bytes because identifiers,
cancellation references, timestamps, and free text are inputs to the production
parser and state-transition behavior under test. Repository documentation and
the versioned capture manifest label the material `TEST DATA ONLY - NOT FOR
NAVIGATION`; the fixture is historical and is never served through Aerobag's
live-feed publication path.

## Pre-Publication History

Before publication, the repository history was replaced with a clean root
containing the audited fixture tree. The retired `notams/incremental-trace/`
SWIM fixture and its blobs are not part of the resulting history.
