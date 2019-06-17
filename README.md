# Headless-Raspberry-Pi-for-Scribblers
Build an interface to make it straightforward for students to configure Scribblers via Raspberry Pi and to program the robot in class.

Useful link: https://www.raspberrypi.org/documentation/remote-access/ip-address.md


#### Headless Connection to Wi-Fi 

Use a usb-SDcard adaptor and read the raspberrypi's SD card. 
Go to the folder ```/boot``` and create a new file named ```wpa_supplicant.conf```

Put in the content:
```
network={
    ssid="wifi/internet name"
    psk="Password"
}
```

Save it. Plug the SD card back in Raspberrypi and run it. 

References:
1) https://learn.adafruit.com/adafruits-raspberry-pi-lesson-3-network-setup/setting-up-wifi-with-occidentalis
