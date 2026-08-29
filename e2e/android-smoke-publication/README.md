# Android Smoke Package Publication

This frozen publication drives the clean-emulator Android E2E suite through
the production Offline Packages discovery, download, verification, install,
and adoption paths. It contains the production NAV23 package
for cycle 2608 and a contract-valid TPP1 package restricted to KPLU plates.
The fixture manifest advertises the KPLU RNAV 35 plate as the native plate
rendering capability backed by those compact package bytes.

The publication is test-only. Its package validity dates are widened so CI is
independent of wall-clock FAA cycles.
