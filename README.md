# Nura — postmarketOS for Samsung Galaxy A22 4G

**Status: experimental bring-up; not boot-tested.**

This repository tracks work toward a postmarketOS port for the Samsung Galaxy A22 4G, model **SM-A225F**, device codename **a22**.

> “Nura” is the project name used here for this device-port effort. It is not an official postmarketOS project rename.

## Known device details

- Device: Samsung Galaxy A22 4G (SM-A225F)
- Codename: `a22`
- SoC family: MediaTek MT6768 / MT6769
- Architecture: ARM64 (`aarch64`)
- Boot image: Android boot header v2, 2048-byte pages
- Device tree compatible string observed in the stock DTB: `mediatek,MT6768`

## Current findings

- The device's stock boot image, recovery image, DTB and DTS were backed up locally before experimentation.
- A Samsung kernel source tree for the A22 was built successfully, but its kernel version differs from the kernel extracted from the installed stock firmware.
- A candidate boot image was assembled from the built kernel and stock ramdisk/DTB for analysis.
- The candidate has **not** been confirmed to boot on the device. Do not treat it as a working image.
- The bootloader's fastboot interface reported `unknown command` for `fastboot boot`; no flash was performed as part of that attempt.

## Safety

Do not flash images from this repository unless you understand the recovery path and have verified the image for your exact model and firmware. The Galaxy A22 has device-specific boot-image and partition requirements. Never reuse offsets or settings from another Samsung model without verification.

## Planned work

- Add a proper postmarketOS device package and kernel package.
- Document reproducible build steps and required dependencies.
- Validate boot image layout against the exact SM-A225F firmware.
- Test boot and hardware support before claiming functionality.

## Related kernel source

The kernel source investigated so far is available at:
https://github.com/Samsung-Helio-G80-Devs/android_kernel_samsung_a22

This repository does not redistribute the full kernel source tree.

## License

Licensing for device-specific files and any future patches must be documented before upstreaming. Respect the licenses of all referenced projects and firmware components.
