Raspberry Pi - Arm Trusted Firmware binaries
============================================

[![Build status](https://img.shields.io/github/workflow/status/pftf/pitf/TF-A%20-%20Raspberry%20Pi%20build.svg?style=flat-square)](https://github.com/pftf/pitf/actions)
[![Github stats](https://img.shields.io/github/downloads/pbatard/pitf/total.svg?style=flat-square)](https://github.com/pbatard/pitf/releases)
[![Release](https://img.shields.io/github/release-pre/pftf/pitf?style=flat-square)](https://github.com/pftf/pitf/releases)

# Summary

This repository is meant to host builds of the Arm Trusted Firmware for use with
the [EDK2 Raspberry Pi UEFI firmwares](https://github.com/tianocore/edk2-platforms/tree/master/Platform/RaspberryPi).

Because of the sensitive nature of these firmware blobs, this process is
accomplished in a fully transparent manner, through GitHub actions, in a way that
allows complete validation that the binaries provided for download have not been
altered from the ones one would build locally using the official TF-A source. 

# Current version

The version of TF-A being built is 2.6, which was released on 2021.11.23.

# Binary validation

The binaries being provided can be validated not to have been altered by
checking the [latest GitHub Actions build log](https://github.com/pftf/pitf/actions)
and confirming that:

- The SHA-1 of the commit that triggered the build is the same as the latest
  commit from this repo (ensures that the built wasn't produced from a "hidden"
  malicious commit that would then have been deleted).
- The TF-A source that was downloaded for the build is the official one that can
  be found at https://git.trustedfirmware.org/TF-A/trusted-firmware-a.git/
- No alterations have been performed to the binary blobs after the build.
- The SHA-256 sums of the binary blobs, which are explicitly displayed as part
  of the build process, do match the SHA-256 sums of the binaries that are
  published on this repository.

Alternatively, you should also be able to clone this repository and produce your
own AppVeyor builds, to confirm that the payloads are identical (only the build
date that is inserted in the binary should change).

# License

[BSD-3-Clause](https://git.trustedfirmware.org/TF-A/trusted-firmware-a.git/tree/docs/license.rst).
