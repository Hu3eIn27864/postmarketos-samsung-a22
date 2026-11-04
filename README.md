# Nura — postmarketOS for Samsung Galaxy A22 4G

**Status: experimental bring-up; not boot-tested.**

This repository tracks work toward a postmarketOS port for the Samsung Galaxy A22 4G, model **SM-A225F**, codename **a22**. “Nura” is a project name for this device-port effort, not an official postmarketOS rename.

## Device identity

- Device: Samsung Galaxy A22 4G (SM-A225F)
- Codename: `a22`
- SoC family: MediaTek MT6768 / MT6769
- Architecture: ARM64 (`aarch64`)
- Boot image: Android boot header v2, 2048-byte pages
- Stock DTB compatible string observed: `mediatek,MT6768`

## Verified findings and limits

- Stock boot, recovery, DTB and DTS were backed up locally before experimentation.
- A Samsung A22 kernel source tree was built, but its kernel version differs from the version extracted from the installed stock firmware.
- A candidate boot image was assembled for analysis.
- The candidate has **not** been confirmed to boot.
- The bootloader's fastboot interface reported `unknown command` for `fastboot boot`; no flash was performed in that attempt.

## Roadmap

See [docs/ROADMAP.md](docs/ROADMAP.md) for staged work and conditional time estimates. The immediate priority is to establish exact firmware compatibility and a safe recovery path before attempting a boot.

## Safety

Do not flash images unless they are verified for the exact SM-A225F model and firmware. Never reuse offsets or settings from another Samsung model. Keep known-good stock boot and recovery images offline and confirm a recovery method before any device write.

## Related kernel source

https://github.com/Samsung-Helio-G80-Devs/android_kernel_samsung_a22

The full kernel source tree is not redistributed here.

## Licensing

Document provenance and licensing for device-specific files and future patches before upstreaming. Respect all referenced projects and firmware licenses.
