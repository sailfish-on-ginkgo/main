# Sailfish OS port to Redmi Note8 devices, LineageOS 16.0 based, aarch64

## About

Please read this document fully before planning or starting to use this port.

This is a community port, meaning that there is no official support and extensions included in the paid version:

* There is no Android app support
* There is no MS exchange support
* There is no Jolla Store predictive text support. Use Presage-based keyboards instead

## How to install

1. download sailfishos zip from [here](https://github.com/sailfish-on-ginkgo/main/releases/).    
2. download Lineageos 16.0 from [here](https://androidfilehost.com/?fid=4349826312261639609), **Audio is not working on others**.
3. download twrp from [here](https://dl.twrp.me/ginkgo/).
4. revert to android9 base miui, and install twrp.
5. install Lineageos 16.0 and boot up to check if everything is ok.
6. reboot to fastboot mode, use `fastboot format:ext4 userdata` to format userdata partition. Need this for fingerprint.
   
   Or you can use TWRP, go to "Wipe -> Advanced Wipe -> Select `Data` and click Repair or Change File System -> Change File System -> EXT4"
8. reboot to recovery mode, send sailfishos zip to your device.
9. flash it use twrp, and reboot.

### How to install waydroid

1. add chum repo `ssu ar sailfishos-chum https://repo.sailfishos.org/obs/sailfishos:/chum/4.6_aarch64/`, be sure you are using the 4.6.0.11 sailfishos.
2. `zypper ref` and `zypper in waydroid-runner waydroid-gbinder-config-hybris`, you can also install them via `Chum GUI`
3. run `waydroid init`, this takes some minutes to download lineageos images.
4. run `systemctl disable --now dnsmasq`
5. replace all `aidl2` to `aidl3` in `/etc/gbinder.d/anbox-hybris.conf`
6. comment or delete `lxc.apparmor.profile = unconfined` in `/var/lib/waydroid/lxc/waydroid/config`
7. `systemctl restart waydroid-container`
8. open Waydroid from launcher, it should be working now

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
  
### Not Working

* Audio record app
* FM radio
* IR remote control





## Issues

https://github.com/sailfish-on-ginkgo/droid-config-ginkgo/issues

## Buy me a coffee

Buy me a coffee to keep this project, thanks! https://paypal.me/birdzhang
