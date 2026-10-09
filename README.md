# OnePlus 15R — BakaSU + SUSFS kernel (6.12.58)

Custom kernel for the **OnePlus 15R (CPH2767, codename macan)** on Android 16, built with GitHub Actions.

## What this build is
- **Kernel:** `6.12.58` on the OnePlus sm8850 common tree, with the 15R's own modules and devicetree
- **Root:** BakaSU, with a matching manager APK from the same commit
- **SUSFS:** v2.3.0
- **Networking:** BBR and BBRv3, CAKE/PIE, TTL target, ip_set
- **Other:** Unicode fix, ADIOS I/O scheduler (default)
- **Tweaks (each applied only if its patch fits the tree):** Boeffla wakelock blocker (empty blocklist), Sultan power/memory patches (optional)
- **Disabled:** Droidspaces, Baseband Guard, NTSync

Tested on CPH2767 firmware 16.0.10.600 only. Keep a boot image backup before flashing.

## Build
Actions → Build and Release OnePlus Kernels → Run workflow on `main`: kernel `android16-6.12`. The root json is pre-filled with the pinned BakaSU commit. Leave the SusFS fields empty.

## Flash
Flash the AnyKernel3 zip with Kernel Flasher and reboot. Check with `uname -r` and `ksu_susfs show version`.

## Credits
- **BakaSU** team, **simonpunk** (SUSFS), **andip71** (Boeffla)
- **OnePlusOSS** (kernel sources), **Google AOSP** and **Qualcomm CLO** (GKI and toolchains)
- **WildKernels** and **Bouteillepleine** for the build framework and kernel patches this repo builds on

All kernel code belongs to its upstream authors.
