---
layout: post
author: redle
title: Root Moto Z Play
---
# Unlock bootloader
Follow the step describe in:
> https://motorola-global-portal.custhelp.com/app/standalone/bootloader/unlock-your-device-a/action/auth


# Root process:
* Tips, use the same version described the bellow link.
> https://forum.xda-developers.com/moto-z-play/how-to/guide-how-to-magisk-root-xposed-oreo-8-t3743273

# Recovery Stock Image Oreo 8.0

Download firmware:
> https://mirrors.lolinet.com/firmware/moto/addison/official/MSTLA/


```
fastboot flash partition gpt.bin
fastboot flash bootloader bootloader.img
fastboot flash logo logo.bin
fastboot flash boot boot.img
fastboot flash recovery recovery.img
fastboot flash dsp adspso.bin
fastboot flash oem oem.img
fastboot flash system system.img_sparsechunk.0
fastboot flash system system.img_sparsechunk.1
fastboot flash system system.img_sparsechunk.2
fastboot flash system system.img_sparsechunk.3
fastboot flash system system.img_sparsechunk.4
fastboot flash system system.img_sparsechunk.5
fastboot flash system system.img_sparsechunk.6
fastboot flash system system.img_sparsechunk.7
fastboot flash system system.img_sparsechunk.8
fastboot flash system system.img_sparsechunk.9
fastboot flash system system.img_sparsechunk.10
fastboot flash modem NON-HLOS.bin
fastboot erase modemst1
fastboot erase modemst2
fastboot flash fsg fsg.mbn
fastboot erase cache
fastboot erase userdata
fastboot reboot
```

# Links:
> https://forums.lenovo.com/t5/MOTOROLA-Android-Developer/Moto-Z-bootloader-unlock-problem-with-quot-bootloader-invalid/td-p/3522737
> https://forum.xda-developers.com/moto-z-play/how-to/guide-how-to-magisk-root-xposed-oreo-8-t3743273
> https://dl.twrp.me/addison/
> https://www.droidmirror.com/downloading/download-magisk-v17-1-zip
> https://github.com/topjohnwu/Magisk/releases

> https://github.com/mame82/P4wnP1_aloa
> https://medium.com/@fbotes2/advance-av-evasion-symantec-and-p4wnp1-usb-c7899bcbc6af
> https://github.com/Jetjames/RaspDucky