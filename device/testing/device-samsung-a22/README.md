# Experimental postmarketOS device package: Samsung Galaxy A22 4G

Target: **Samsung Galaxy A22 4G (SM-A225F)**, MediaTek MT6768-family SoC.

**This is metadata scaffolding, not a working port. Do not flash anything from this branch.**

The package deliberately sets `deviceinfo_flash_method="none"` and does not define a kernel package, DTB path, boot image generation, or persistent-partition flashing procedure. Those details must be validated against the exact device firmware and bootloader before they are configured.

Required next steps:

1. Match the kernel source to the exact installed firmware/kernel version.
2. Add a reproducible `linux-samsung-a22` package and document its config and patches.
3. Determine the correct Android boot-image packaging and initramfs integration.
4. Build the package/image in pmbootstrap and run static checks.
5. Establish a safe test/recovery path, collect boot logs, and test hardware before claiming boot support.

Reference notes: see the repository's `docs/bring-up-notes.md` and `docs/artifact-inventory.md`.
