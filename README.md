# Headless-Raspberry-Pi-for-Scribblers
Build an interface to make it straightforward for students to configure Scribblers via Raspberry Pi and to program the robot in class.

Use a usb-SDcard adaptor and read the raspberrypi's SD card. 

Go to the folder '''/boot''' and create a new file named '''wpa_supplicant.conf'''

Put in the conetent:

'''
network={
    ssid="wifi/internet name"
    psk="Password"
}
'''

Save it. Plug the SD card back in Raspberrypi and run it. 
