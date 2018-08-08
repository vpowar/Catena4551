# LoRaWAN_SensorNetworks-Catena
This repository is a work-in progress under the Intelligent River v2.0 project at Clemson University,SC. The goal is to interface Catena 4551 OR Catena 4450/4470 with Adafruit Feather M0, developed by [MCCI Corporation](http://www.mcci.com/mcci-v5/index.html) with different environmental sensors for water,air and soil quality monitoring. This project is based on [LoRaWAN](https://lora-alliance.org/about-lorawan) (Low Power Wide Area Network) designed to wirelessly connect battery operated ‘things’ to the internet in regional, national or global networks, and targets key Internet of Things (IoT) requirements such as bi-directional communication, end-to-end security, mobility and localization services. Thus, we have implemented a bunch of IoT nodes on different Clemson streams and channels to monitor rain water inflow and storm water wash-off. IoT nodes by definition are controllers coupled with environmental sensors, that act as radio nodes(or modules) connected to central gateway for IoT purposes.

For more details about the project                       :   http://river.info/     

For more details on the controller board(data logger)    :   https://github.com/mcci-catena  
(Catena 4551 OR Catena 4450/4470)

For more details on network & data connectivity platform :   https://www.thethingsnetwork.org/ 

## Getting Started
These instructions will get you a copy of the project up and running for development and testing purposes. See deployment for notes on how to deploy the project on a live system. You will need the following hardware platforms/controller boards and softwares, libraries etc. before you dive straight into IoT communication. 

### Prerequisites 
It is advisable to have following controller platforms:
#### Controller Platforms:
````
1. Adafruit Feather M0 and 
2. Catena Wing 4450/4470 
`````
OR
``````
1. Catena 4451
``````
Other controller boards might work but aren't tested yet. 

#### Software 
Install Arduino IDE
### Installation 
Follow steps [here](https://github.com/mcci-catena/Catena-Sketches/blob/master/catena4450m101_sensor/README.md) for installing and setting up Catena Boards. It is advisable to visit: https://github.com/mcci-catena/Catena-Sketches and https://github.com/mcci-catena/Catena-Sketches/blob/master/catena4450m101_sensor/README.md before you proceed any further with this document and code structure. **This repository consists is based on top of the code developed by MCCI and is only an *extension/ modification* of base code.** 

## Uploading Code
Follow the steps before to upload the code to the boards. The feather and catena stack has easy interface of code 
### Feather M0 with Catena 4450/4470 wings

### Catena 4551 (Standalone)




