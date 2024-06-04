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
7. reboot to recovery mode, send sailfishos zip to your device.
8. flash it use twrp, and reboot.


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
  
### Not Working

* Camera
* FM radio
* IR remote control

## Issues

https://github.com/sailfish-on-ginkgo/droid-config-ginkgo/issues

## Buy me a coffee

Buy me a coffee to keep this project, thanks! https://paypal.me/birdzhang
