# Galaxy A22 bring-up notes

These notes record observations from one SM-A225F setup. Verify them against the target device before relying on them.

## Firmware and boot image

- Observed firmware build: `A225FXXSBDYE1`
- Kernel source branch investigated: `A225FXXU6DWE3`
- Stock boot header: v2
- Page size: 2048 bytes
- Kernel load address observed in stock boot image: `0x40080000`
- Ramdisk address: `0x47c80000`
- Tags address: `0x4bc80000`
- Boot command line observed: `bootopt=64S3,32N2,64N2`
- Embedded DTB offset in the stock boot image: `0x1195000`
- Stock DTB compatible string: `mediatek,MT6768`

The stock kernel extracted from the installed firmware reported version `4.14.364-lineage-WMK+`, while the investigated source tree is based on a 4.14.186 kernel. This version difference is significant and requires validation.

## Observed partition identifiers

The PIT inspection reported the following partition IDs:

| Partition | PIT identifier |
| --- | ---: |
| dtbo | 13 |
| vbmeta | 14 |
| boot | 36 |
| recovery | 37 |
| super | 43 |
| userdata | 49 |

These are observations from the inspected device, not universal instructions. Confirm the PIT and exact model before any write operation.

## Kernel source and build observations

Source repository:
https://github.com/Samsung-Helio-G80-Devs/android_kernel_samsung_a22

Investigated branch: `A225FXXU6DWE3`

The kernel source tree built successfully using an Android-era GCC/Clang toolchain. The resulting DTB matched the extracted stock DTB by SHA-256 in the investigated build. A successful compile and matching DTB do **not** establish that the kernel can boot or that hardware works.

## Validation still required

- Reconcile kernel source version with the exact firmware.
- Confirm boot image header and vendor boot expectations for the target firmware.
- Verify kernel configuration and initramfs integration.
- Boot without writing to persistent partitions if a supported method becomes available.
- Confirm serial or kernel logs, root filesystem mount, display, touch, storage, Wi-Fi, audio, modem and suspend.
- Only then document a tested installation procedure.

## Do not flash yet

The assembled candidate image was not boot-tested. No successful boot has been confirmed. Keep stock boot/recovery backups and their hashes outside this repository; do not publish personal backups or proprietary firmware images.
