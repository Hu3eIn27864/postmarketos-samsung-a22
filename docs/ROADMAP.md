# Samsung Galaxy A22 4G (SM-A225F) Bring-up Roadmap

**Current state:** experimental research; no successful boot is confirmed. Estimates are conditional on obtaining a kernel/device-tree combination compatible with the exact stock firmware.

## M0 — Evidence and recovery baseline (1–2 weeks)
- [ ] Record exact model, firmware build, bootloader revision and partition map.
- [ ] Keep verified stock boot/recovery backups offline.
- [ ] Document kernel source commit and version mismatch.
- [ ] Identify safe recovery procedure before any device write.
**Exit:** reproducible device facts and recovery plan.

## M1 — Kernel/device package (3–6 weeks)
- [ ] Create postmarketOS device package with verified deviceinfo.
- [ ] Create reproducible kernel package/configuration.
- [ ] Validate boot image header, page size, DTB placement and ramdisk assumptions.
- [ ] Build in a clean pmbootstrap environment.
**Exit:** reproducible artifacts pass static checks; not yet a boot claim.

## M2 — First boot attempt (2–6 weeks)
- [ ] Establish a supported boot path for this exact bootloader.
- [ ] Capture serial/logcat/kernel logs where possible.
- [ ] Test only with a verified recovery route.
**Exit:** boot reaches a documented milestone or failure is isolated.

## M3 — Hardware validation (1–3 months after first boot)
- [ ] Display, touch and backlight.
- [ ] Storage, Wi-Fi and Bluetooth.
- [ ] Audio, cameras, sensors and charging.
- [ ] Suspend/resume and thermal behavior.
**Exit:** per-device test matrix with logs and known limitations.

## Planning note

These ranges are not calendar promises. If bootloader restrictions or kernel ABI incompatibilities block progress, re-scope before attempting additional flashing. Never treat a candidate image as bootable until tested on the exact SM-A225F variant.
