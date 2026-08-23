# Release-Journey Publication

Contract-valid compact publication used by the cross-platform product-release
journeys. `fixture.json` identifies capability-bearing records; the packaged
publication is materialized after checkout so Android can install packages and
web can fault unpacked resources from the same immutable fixture.

Regenerate this directory with
`tools/ci/build_release_journey_fixture.py`, then validate it with
`tools/ci/materialize_release_journey_fixture.py` and the release-journey
foundation tests in the Aerobag application repository.
