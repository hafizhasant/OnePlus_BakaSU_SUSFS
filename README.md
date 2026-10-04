# OnePlus 15R — ReSukiSU + SUSFS kernel (6.12.58)

Custom kernel for the **OnePlus 15R (CPH2767, codename macan)** on Android 16, built with GitHub Actions.

## What this build is
- **Kernel:** `6.12.58-android16-6-o-g96c5b8ea00fb-4k` (OnePlus sm8850 Pad 4 common tree + the 15R's own modules/devicetree)
- **Root:** ReSukiSU, **SUSFS:** v2.3.0
- **Networking:** BBR + BBRv3, CAKE/PIE, TTL target, ip_set
- **Other:** NTSync, Droidspaces, Baseband Guard, Unicode fix
- **Tweaks (each applied only if its patch fits the tree):** ADIOS I/O scheduler (default), Boeffla wakelock blocker (empty blocklist), Sultan power/memory patches

Tested on CPH2767 firmware 16.0.10.600 only. Keep a boot image backup before flashing.

## Build
Actions → Build and Release OnePlus Kernels → Run workflow on `main`: kernel `android16-6.12`, root json `[{"type":"ksun","hash":"main"}]` (internal name; installs ReSukiSU), SusFS fields empty. The build log lists which tweaks applied or were skipped.

## Credits
- **WildKernels** — OnePlus_KernelSU_SUSFS framework and kernel_patches (this repo is a fork)
- **Bouteillepleine** — OnePlus-ReSukiSu_NMS integration, kernel_patches (ADIOS) and AnyKernel3
- **ReSukiSU** team, **simonpunk** (SUSFS), **andip71** (Boeffla), **OnePlusOSS**, **Google AOSP** and **Qualcomm CLO**

All kernel code belongs to its upstream authors.
