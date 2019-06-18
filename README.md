# Headless-Raspberry-Pi-for-Scribblers
Build an interface to make it straightforward for students to configure Scribblers via Raspberry Pi and to program the robot in class.
Useful link: https://www.raspberrypi.org/documentation/remote-access/ip-address.md

The instructions are settup for:

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


#### Obtaining the IP addr. of raspberrypi

On the computer, run command:
```sudo nano /media/stuadmin/root/etc/rc.local```

Add these two lines of code into ```rc.local```:
```sleep 30s```
```hostname -I > /home/pi/Desktop/raspIP.txt```
The first line gives the pi some time to connect to the internet, and the second line saves its ip address into the .txt file on Raspberry pi's Desktop.

Plug the SD back into Raspberry pi and boot it. Wait for a minute to let the program obtain the ip. 

Load the SD card into the computer and obtrain the ip addr.

References:
1) https://www.raspberrypi.org/documentation/linux/usage/rc-local.md

#### SSH Rasperrypi
Run the command with the obtained ip:
```ssh pi@10.10.159.161```

The default username/passord should be pi/raspberry.






