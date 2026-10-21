# Local build artifact inventory

**Status: experimental; the candidate has not been boot-tested.** This file records artifacts known to exist on the developer's Ubuntu workstation. It does not contain the binary images themselves.

## A22 boot candidate

Local path: `~/a22-backup/boot-analysis-mkbootimg/boot-candidate-bootfix.img`

- Size: 16,586,752 bytes
- SHA-256: `1df0e4b627391e793a224468eb4cdecf5be7b58b5f1b6cb86bf5f2d4f49aa399`
- Built from the experimental kernel image plus the original stock ramdisk and DTB.
- Component extraction/verification was performed locally.
- **Not confirmed to boot. Do not flash based on this record alone.**

## Kernel build outputs

Local project: `~/a22-kernel-work/samsung-a22-kernel`

- Kernel source repository: https://github.com/Samsung-Helio-G80-Devs/android_kernel_samsung_a22
- Investigated branch: `A225FXXU6DWE3`
- Investigated commit: `d945649ac0ec8b62cce67d8043012854a84d69b7`
- `out/arch/arm64/boot/Image`: SHA-256 `e9050147febc2d1988748fedf075e0e11558d228903552138a79d974086406c1`
- `out/arch/arm64/boot/Image.gz`: SHA-256 `92c4671202207112aca415c65f2ac50ed2101927cae5a9f3d815bfa5ec24e017`
- `out/arch/arm64/boot/mt6768.dtb`: SHA-256 `2a8663e228412eed4784156da1afb3edbc8408ec190642b459e54b48efd231a7`

## Original device backups

Stock `boot.img`, `recovery.img`, extracted DTBs/DTS and related analysis files are stored locally under `~/a22-backup/`. They are intentionally **not uploaded here**: stock firmware-derived images may be large and should remain safely backed up locally. Keep at least one untouched copy outside the working directory.

Known hashes:
- Original `boot.img`: `26c0b72280530ebfe66fd5deb202596d916053aeb4ed4941f6cad1a1e6c669f3`
- Original `recovery.img`: `5366817bfc6ac5c2b41fcabb35c82dd989c9f54229cdbaee2da9fff244c19f92`

## Test outcome

The attempt to use `fastboot boot` returned `FAILED (remote: 'unknown command')`. That means the candidate was not boot-tested by that method; it does **not** prove the image itself fails. No flash was performed during that attempt.

Next steps: establish a safe, model-specific test/recovery procedure; then record boot logs and hardware results. Do not claim a successful port until the device has actually booted and been tested.
