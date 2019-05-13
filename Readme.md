Raspberry Pi3 - Arm Trusted Firmware binaries
=============================================

[![Build status](https://img.shields.io/appveyor/ci/pbatard/pitf.svg?style=flat-square)](https://ci.appveyor.com/project/pbatard/pitf)
[![Github stats](https://img.shields.io/github/downloads/pbatard/pitf/total.svg?style=flat-square)](https://github.com/pbatard/pitf/releases)

# Summary

This repository is meant to host builds of the Arm Trusted Firmware for use with
the [EDK2 Raspberry Pi 3 UEFI firmwware](https://github.com/tianocore/edk2-platforms/tree/master/Platform/RaspberryPi/RPi3).

Because of the sensitive nature of these firmware blobs, this process is
accomplished in a fully transparent manner, through AppVeyor, and in a way that
allows complete validation that the binaries provided for download have not been
altered from the ones one would build locally using the official ATF source. 

# Current version

The version of ATF being built is 2.1, which was released on 2019.03.29.

# Binary validation

The binaries being provided can be validated not to have been altered by
checking the [latest AppVeyor build log](https://ci.appveyor.com/project/pbatard/pitf)
and confirming that:

- The SHA-1 of the commit that triggered the build is the same as the latest
  commit from this repo (ensures that the built wasn't produced from a "hidden"
  malicious commit that would then have been deleted).
- The ATF source that was downloaded for the build is the official one that can
  be found at https://github.com/ARM-software/arm-trusted-firmware/archive/
- No alterations have been performed to the binary blobs after the build.
- The SHA-256 sums of the binary blobs, which are explicitly displayed as part
  of the build process, do match the SHA-256 sums of the binaries that are
  published on this repository.

Alternatively, you should also be able to clone this repository and produce your
own AppVeyor builds, to confirm that the binaries are identical.

# License

[BSD-3-Clause](https://github.com/ARM-software/arm-trusted-firmware/blob/master/license.rst).
