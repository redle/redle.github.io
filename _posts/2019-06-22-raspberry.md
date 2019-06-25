---
layout: post
author: redle
title: USB Bad
---

## Configure wifi

Edit /etc/network/interfaces and add follow lines:
```
auto wlan0
iface wlan0 inet dhcp
       wpa-ssid network-name
       wpa-psk pre-shared-key
```

# Links:
> https://www.raspberrypi.org/downloads/raspbian/
> https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md
> https://raspberrypihq.com/how-to-connect-your-raspberry-pi-to-wifi/
