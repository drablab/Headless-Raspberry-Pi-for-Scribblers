# Headless-Raspberry-Pi-for-Scribblers
Build an interface to make it straightforward for students to configure Scribblers via Raspberry Pi and to program the robot in class.
Useful link for wireless connection in general: https://www.raspberrypi.org/documentation/remote-access/ip-address.md

The hardware used for this settup are:
Raspberry pi 3b+, a computer with Ubuntu Linux

#### Headless Connection to Wi-Fi 
This step writes a boot program into the raspberrypi so it connects to the desired wifi at boot up automatically. 

Use a usb-SDcard adaptor and read the raspberrypi's SD card. 
Go to the folder ```/boot``` and create a new file named ```wpa_supplicant.conf```

Put in the file ```wpa_supplicant.conf``` the content:
```
network={
    ssid="wifi/internet name"
    psk="Password"
}
```
Note that ```ssid``` is your the wifi name and ```psk``` is the password of the wifi that you're connecting to (both your computer and raspberrypi)
Save the file. Plug the SD card back in Raspberrypi and boot the pi. 

References:
1) https://learn.adafruit.com/adafruits-raspberry-pi-lesson-3-network-setup/setting-up-wifi-with-occidentalis


#### Obtaining the IP addr. of raspberrypi
This step saves the IP addr in the SD card in order to complete the last step of ssh(secured shell) connenction.

On the computer, run command:
```sudo nano /media/stuadmin/root/etc/rc.local```

Add these two lines of code into ```rc.local```:

```sleep 30s```

```hostname -I > /home/pi/Desktop/raspIP.txt```

The first line gives the pi some time to connect to the internet, and the second line saves its ip address into the .txt file on Raspberry pi's Desktop.

Plug the SD back into Raspberry pi and boot it. Wait for a minute to let the program obtain the ip. 

Load the SD card into the computer and obtrain the ip addr. Press ```Ctrl-X``` and ```y``` and ``` enter``` to save the modied changes in the default linux nano editor.

References:
1) https://www.raspberrypi.org/documentation/linux/usage/rc-local.md

#### SSH Rasperrypi
This step allows one to gain full access to a rasberrypi terminal on a Ubuntu linux computer.

Run the command with the obtained ip(the ip here is 10.10.159.161):
```ssh pi@10.10.159.161```

To log in, the default username/passord should be pi/raspberry.

Finally, access the pi terminal.
