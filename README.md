# LoRaWAN_SensorNetworks-Catena

This repository is a work-in progress under the Intelligent River v2.0 project at Clemson University,SC. The goal is to interface Catena 4551 OR Catena 4450/4470 with Adafruit Feather M0, developed by [MCCI Corporation](http://www.mcci.com/mcci-v5/index.html) with different environmental sensors for water,air and soil quality monitoring. This project is based on [LoRaWAN](https://lora-alliance.org/about-lorawan) (Low Power Wide Area Network) designed to wirelessly connect battery operated ‘things’ to the internet in regional, national or global networks, and targets key Internet of Things (IoT) requirements such as bi-directional communication, end-to-end security, mobility and localization services. Thus, we have implemented a bunch of IoT nodes on different Clemson streams and channels to monitor rain water inflow and storm water wash-off. IoT nodes by definition are controllers coupled with environmental sensors, that act as radio nodes(or modules) connected to central gateway for IoT purposes.

For more details about the project                       :   http://river.info/     
For more details on the controller board(data logger)    :   https://github.com/mcci-catena  
(Catena 4551 OR Catena 4450/4470)
For more details on network & data connectivity platform :   https://www.thethingsnetwork.org/ 

## Getting Started
These instructions will get you a copy of the project up and running for development and testing purposes. See deployment for notes on how to deploy the project on a live system. You will need the following hardware platforms/controller boards and softwares, libraries etc. before you dive straight into IoT communication. 
### Prerequisites 
#### Controller Platforms:
It is advisable to have following controller platforms:
````
1. Adafruit Feather M0 and 2. Catena Wing 4450/4470  OR
1. Catena 4451
`````` 
Other controller boards might work but aren't tested yet. 
#### Software 
Install Arduino IDE. Follow steps [here](https://www.arduino.cc/en/Main/Software): 

### Installation 
Follow steps [here](https://github.com/mcci-catena/Catena-Sketches/blob/master/catena4450m101_sensor/README.md) for installing and setting up Catena Boards. It is advisable to visit: https://github.com/mcci-catena/Catena-Sketches and https://github.com/mcci-catena/Catena-Sketches/blob/master/catena4450m101_sensor/README.md before you proceed any further with this document and code structure. **The contents of this repository are based on top of the code developed by MCCI and this is only an *extension/ modification* of skeleton code.** Different sensors have been interfaced on top of MCCI's code in this repo. 

## Uploading Code
Follow the steps before to upload the code to the boards. The feather and catena stack has easy interface of code 
### Feather M0 with Catena 4450/4470 wings
Follow steps [here](https://github.com/mcci-catena/Catena-Sketches/blob/master/catena4450m101_sensor/README.md) to get started with 4450 and 4470 catena wings. 
### Catena 4551 (Standalone)
There are two methods to upload code, 
``` 1. DFU ```
``` 2. ST-Link.```

I have tested the DFU mode with the help of MCCI and below is the procedure I followed; note that based on your working environment you would have to follow different procedures. 
#### WINDOWS: 
1. INSTALL ZADIG:

You would have to install Zadig from here: https://zadig.akeo.ie/. This software is used to set the driver address. Download and install the software. Launch the .exe icon. 

2. Next, Short BOOT0 and VDD+ with a jumper wire on the 4551 board and press reset. This enables the bootloading mode to transfer code to the board.See the images below for deatiled understanding.
 ![alt text](https://github.com/vpowar/LoRaWAN_SensorNetworks-Catena/blob/master/catena4551_connection.jpg "catena4551_jumper connection")
    
 3. On the Zadig terminal- Select Options -> List All Devices
 ![alt text](https://github.com/vpowar/LoRaWAN_SensorNetworks-Catena/blob/master/extra/Zadig_01.png "Zadig Options")
 
 4. Select STM32 BOOTLOADER from the device dropdown
 
 5. Select WinUSB (v6.1.7600.16385) as new driver
 
 6. Click Replace Driver
 
![alt text](https://github.com/vpowar/LoRaWAN_SensorNetworks-Catena/blob/master/extra/Zadig_02.png "Zadig Options")
 
 
 7. Now setup is ready. You can compile and upload your code using DFU.
  Before you upload your code make sure your arduino terminal has the following options selected.
  
  ````TOOLS --> SERIAL INTERFACE - "NO SERIAL" && UPLOAD METHOD - DFU" && USB INTERFACE - "USB SERIAL" && PROGRAMMER - "STM 32 BOOTLOADER"````
  
  ![](https://github.com/vpowar/LoRaWAN_SensorNetworks-Catena/blob/master/extra/ArduinoSettings.png|height=48)
  
  #### LINUX:
  
  1. Install the rules from [drivers/linux/mccicatena4551.rules](https://github.com/mcci-catena/Arduino_Core_STM32/tree/master/drivers/linux)
 On a terminal you can simply do the following: 
  
  - `````$wget https://raw.githubusercontent.com/mcci-catena/Arduino_Core_STM32/master/drivers/linux/mccicatena4551.rules `````
  
  - `````$mv /downloaded_filelocation/mccicatena4551.rules /etc/udev/rules.d `````
  
  2. Reload rules or Restart dbus deamon
  - ````` $udevadm control --reload-rules `````
  
  - Give root permissions using 'sudo' whenever necessary. Make sure and ensure your user is in the plugdev group. 
  
  - You can check by typing `````$groups USERNAME `````
  
  - OR add your $USER to plugdev by typing: 
  
  ````` sudo adduser USERNAME plugdev ````` 
  
  Once your $USER has plugdev previliges, you are all set to go. 
  
  - Alternatively you could also restart the dbus deamon by typing
  
  ````` kill -HUP pid`````
  
  3. Reboot the computing device to ensure all changes have taken place. 
  
  #### MAC OS X and CHROMEBOOK: 
  The board will just plug in and work, without drivers!
   
  
