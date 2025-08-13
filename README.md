# Sailfish OS port to Redmi Note8 devices, LineageOS 16.0 based, aarch64

## About

Please read this document fully before planning or starting to use this port.

This is a community port, meaning that there is no official support and extensions included in the paid version:

* There is no Android app support
* There is no MS exchange support
* There is no Jolla Store predictive text support. Use Presage-based keyboards instead

## How to install

1. Download sailfishos zip from [here](https://github.com/sailfish-on-ginkgo/main/releases/).    
2. Download Lineageos 16.0 from [here](https://androidfilehost.com/?fid=4349826312261639609) or [here](https://github.com/sailfish-on-ginkgo/main/releases/download/0.5.0.0.55/lineage-16.0-20191121-UNOFFICIAL-ginkgo.zip) , **Audio is not working with others**.
3. Download twrp from [here](https://dl.twrp.me/ginkgo/).
4. Revert to android9 base miui, and install twrp.(Mine is ginkgo_global_images_V11.0.12.0.PCOMIXM_20201119.0000.00_9.0_global_37804edbcb.tgz)
5. Install Lineageos 16.0 and boot up to check if everything is ok.
6. Reboot to fastboot mode, use `fastboot format:ext4 userdata` to format userdata partition. Need this for fingerprint.
   
   Or you can use TWRP, go to "Wipe -> Advanced Wipe -> Select `Data` and click Repair or Change File System -> Change File System -> EXT4"
8. Reboot to recovery mode, send sailfishos zip to your device.
9. Flash it use twrp, and reboot.
10. Check sound is working or not, if it's not working, flash [this vendor](https://github.com/TryHardDood/mi-vendor-updater/releases/download/ginkgo_global-stable/fw-vendor_ginkgo_miui_GINKGOGlobal_V11.0.11.0.PCOMIXM_793f382e0d_9.0.zip) via twrp. If sound still not works, drop your issue to https://github.com/sailfish-on-ginkgo/main/issues/1 

### How to install waydroid

1. add chum repo `ssu ar sailfishos-chum https://repo.sailfishos.org/obs/sailfishos:/chum/5.0_aarch64/`, be sure you are using 5.0 version sailfishos.
   (If you are using 5.1 or greater version, check if your sfos version https://repo.sailfishos.org/obs/sailfishos:/chum/ exist or not, and chang the url to correct one.)
2. `zypper ref` and `zypper in waydroid-runner waydroid-gbinder-config-hybris`, you can also install them via `Chum GUI`
3. run `waydroid init`, this takes some minutes to download lineageos images. Already have system.img and vendor.img? use [this way to init ](https://docs.waydro.id/faq/using-custom-waydroid-images)
4. run `systemctl disable --now dnsmasq`
5. ~~replace all `aidl2` to `aidl3` in `/etc/gbinder.d/anbox-hybris.conf`~~ (not needed now)
6. ~~comment or delete `lxc.apparmor.profile = unconfined` in `/var/lib/waydroid/lxc/waydroid/config`~~ (not needed now)
7. `systemctl restart waydroid-container`
8. open Waydroid from launcher, it should be working now.

## Current state

### Working

* Audio
* Display
* Touch, multitouch
* Calls
* Cellular network
* LED
* Bluetooth
* GPS
* WLAN (connect and hotspot)
* GSM (SMS, voice, data)
* Keys (Vol +/-, camera, power)
* Power management
* USB Charging, Network, MTP
* Sensors
* Vibrator
* SD card (not tested)
* Fingerprint
* Waydroid
* Camera
* IR remote control (Working on Waydroid, tested by @clasxg)
    
### Not Working

* Audio record app
* FM radio






## Issues

https://github.com/sailfish-on-ginkgo/main/issues

join telegram: @sailfish_on_ginkgo


## Buy me a coffee

Buy me a coffee to keep this project, thanks! https://paypal.me/birdzhang
