# OnePlus Nord N200 (dre): VoltageOS manifest

A local manifest for building an unofficial VoltageOS 16.2 (Android 16) port for the OnePlus Nord N200 (`dre`, DE2117).

These builds are unofficial. They are based on VoltageOS and on the LineageOS device tree for dre, and are not affiliated with either project.

## What's in the manifest

| Path | Repo | Branch |
|---|---|---|
| `device/oneplus/dre` | android_device_oneplus_dre_VOS_Test | voltage-16.2 |
| `hardware/oplus` | android_hardware_oplus_VOS_Test | voltage-16.2 |
| `kernel/oneplus/sm4350` | android_kernel_oneplus_sm4350_VOS_Test | lineage-23.2 |
| `vendor/oneplus/dre` | proprietary_vendor_oneplus_dre_VOS_Test | lineage-23.2 |

The device and hardware branches carry the changes needed for VoltageOS (product file renamed to `voltage_dre`, `vendor/voltage` and `device/voltage` paths, and a Doze fix). The kernel and vendor repos are unmodified forks of LineageOS and TheMuppets.

## Usage

Copy `dre.xml` into `.repo/local_manifests/` of a VoltageOS 16.2 tree, then sync only these projects:

    repo sync -c --no-tags device/oneplus/dre hardware/oplus kernel/oneplus/sm4350 vendor/oneplus/dre

Then build with `breakfast dre userdebug`. Note: syncing from a clean checkout has not been tested yet.

## Status

Tested so far: builds, installs by sideload, boots, and runs. GmsCompat works with Sandboxed Google Play installed from the GrapheneOS app store.

Known change: the Lineage-only proximity check on pick-up-to-wake was replaced with a plain wake call, so the screen may light up in a pocket.

Everything else (camera, calls, VoLTE, fingerprint, T-Mobile variant) is still being tested.

## BensonBuilds

These builds are dedicated to Benson, who lived to be 18. Years ago, every time the Xbox 360 was turned on, he would run to the TV and bat at the logo as it animated. He is missed.
