![OTAUpdater Header](http://img.vmobi.us/logo.png)



Vmobi Updater
==========
Vmobi Updater is based on the [OTA Update Center](https://otaupdatecenter.pro/) and is an update application for roms/devices supported by [Team Vmobi](http://vmobi.us).

Vmobi Developers
==========
Add this lines to your build.prop:

    otaupdater.otaid=(write your ota id here without spaces or brackets)
    otaupdater.otaver=(write your ota version here without spaces or brackets)
    otaupdater.otatime=(write the date+time here as: 20120820-1516 without spaces or backets)

If your device has some quirky sdcard (not /sdcard) naming in the OS or recovery, add these lines to your build.prop:

    otaupdater.sdcard.os=(sdcard name (e.g. sdcard2 for /sdcard2) in the main system here without spaces or brackets)
    otaupdater.sdcard.recovery=(sdcard name (e.g. sdcard2 for /sdcard2) in recovery here without spaces or brackets)
    
If your device cannot be rebooted with "adb shell reboot recovery", write a script that reboots your device and add these lines to your build.prop:
If you cannot write such a script, use $$NULL$$ instead of the path - the app will then only try to reboot via PowerManager.

    otaudpater.rebootcmd=/path/to/rebootscript.sh -OR- $$NULL$$

If auto-flashing a ROM will do bad things to your device, and the user needs to flash manually, add the following to your build.prop:

    otaupdater.noflash=1

Go to: [OTA Update Center](https://otaupdatecenter.pro/) to register an account, and add/update your rom.

How to Build
==========
Make sure you have API 15 installed in for the Android SDK. Then add to Eclipse, make your changes and export as an Android application.

      $ git clone git@github.com:vmobi-jfltevzw/android_packages_apps_VmobiUpdater.git
      
