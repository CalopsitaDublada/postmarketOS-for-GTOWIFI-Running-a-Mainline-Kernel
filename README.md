# postmarketOS-for-GTOWIFI-Running-a-Mainline-Kernel
This is the postmarketOS port with the 7.1.3 mainline kernel for the Galaxy Tab A8.0 2019 (or *gtowifi*, if you prefer).

# postmarketOS for Samsung Galaxy Tab A 8.0 (2019) Wi-Fi

Linux Mainline on the Samsung Galaxy Tab A 8.0 (2019) Wi-Fi.

> Status: Work in progress — experimental port.

## About

This project aims to bring postmarketOS to the Samsung Galaxy Tab A
8.0 (2019) Wi-Fi, also known as the SM-T290 (`gtowifi`).

The goal is to run Alpine Linux with a mainline Linux kernel, using
the existing lk2nd bootloader port and device-specific hardware support.

This is an independent community project and is not affiliated with
Samsung, Qualcomm, LineageOS, or the postmarketOS project.

## Device

| Component | Information |
|---|---|
| Device | Samsung Galaxy Tab A 8.0 (2019) Wi-Fi |
| Model | SM-T290 |
| Codename | gtowifi |
| SoC | Qualcomm Snapdragon 429 |
| Architecture | ARM64 |
| Bootloader | lk2nd |
| Target OS | postmarketOS |
| Base distribution | Alpine Linux |
| Kernel | Linux Mainline, msm89x7 |

## Project Goals

- Boot postmarketOS on the SM-T290.
- Integrate the msm89x7 Mainline kernel.
- Configure the correct Device Tree Blob (DTB).
- Reuse the existing lk2nd port where compatible.
- Investigate DRM/KMS display support.
- Enable touchscreen, Wi-Fi, audio, and other hardware.
- Provide reproducible build instructions.
- Document known issues and development progress.

## Display Support

Display support is a major development target.

The project will investigate the Mainline kernel's display pipeline,
including:

- Qualcomm display controller support.
- MIPI DSI connectivity.
- LCD panel initialization.
- Backlight control.
- DRM/KMS.
- Mesa and GPU acceleration.

The Android display HAL is not assumed to be a requirement for the
native Linux graphics stack. Compatibility components may be
investigated if necessary.

Hardware support will be documented as it is tested.

## Boot Process

The intended boot sequence is:

1. Device bootloader.
2. lk2nd.
3. Linux Mainline kernel.
4. Device Tree Blob (DTB).
5. postmarketOS initramfs.
6. Alpine Linux root filesystem.
7. Linux graphical environment.

The boot image format will be selected according to the capabilities
of the lk2nd version used by the device.

Android boot image header v2 is the initial target, subject to
compatibility verification.

## Building

Build instructions are currently under development.

The intended build environment is Linux with pmbootstrap and the
required Android/Linux kernel build dependencies.

The build process will eventually cover:

1. Preparing the build environment.
2. Configuring the device package.
3. Configuring and compiling the kernel.
4. Building the DTB.
5. Packaging the kernel and initramfs.
6. Building the postmarketOS root filesystem.
7. Testing the boot process.

See [docs/BUILDING.md](docs/BUILDING.md) when available.

## Current Status

This port is experimental.

The existing postmarketOS port has been tested on the device, but
successful operation of the Mainline kernel with the complete
postmarketOS userspace has not yet been established.

Current development priorities:

- [ ] Inspect the existing lk2nd port.
- [ ] Prepare the device configuration.
- [ ] Integrate the Mainline kernel.
- [ ] Verify DTB and boot image compatibility.
- [ ] Boot the postmarketOS initramfs.
- [ ] Mount the root filesystem.
- [ ] Diagnose display initialization.
- [ ] Start a graphical environment.
- [ ] Test additional hardware.

## Contributing and Project Authorization

This project is maintained by its original project owner.

Please contact the maintainer before proposing to take over or
continue project maintenance independently.

Contributions, patches, and improvements should be discussed with
the maintainer before integration.

This project does not grant blanket permission to represent oneself
as its maintainer or to take over the official project.

Applicable copyright and licensing terms remain in effect.

## Disclaimer

This software is experimental and may contain bugs.

Do not assume that all hardware features work.

Back up important data before testing boot images or modifying device
partitions. Prefer non-destructive testing methods whenever possible.

The maintainers are not responsible for damage caused by misuse
of the software.

## License

The project license will be specified before the first public release.

Third-party components remain subject to their respective licenses.

## Acknowledgments

- The postmarketOS community.
- The Linux kernel community.
- The lk2nd developers.
- Contributors to msm89x7 Mainline support.
- Developers working on the gtowifi Linux and Android ports.
