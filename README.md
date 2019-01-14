# MAX & NodeRED on Raspberry Pi

This project contains two seperate NodeRED flows that can run on ony Raspberry Pi 3 with a camera, which will illustrate the use of using NodeRED and IoT devices to interact with Deep Learning Models from the Model Asset eXchange. These flows also interact with a Seperate NodeRED flow that can be deployed on IBM Cloud, which presents a publicly accesible and configurable dashboard to display the output.


## Pre-requisites:
1. Raspberry Pi
2. Micro SD Card (8GB or larger recommended)
3. Raspberry Pi Camera
4. Bluemix Account


## Table of Contents

1. Set Up The Raspberry Pi

2. Set Up IBM Cloud & Watson IoT Connections

3. Import the NodeRed Flows

4. Edit the Necessary Nodes

5. Interact with MAX Models Through Dashboard

——————————

### Step 1: Set Up The Raspberry Pi

#### _If you are starting with a brand new Raspberry Pi, follow these steps to install Raspbian with NOOBS (your Operating System)._
1. Download NOOBS at this link: https://downloads.raspberrypi.org/NOOBS_latest and extract the NOOBS folder from the zip file._
2. To format your Micro SD card for NOOBS, you will need a single FAT32 partition. I recommend the free software ApplePi Baker (https://www.tweaking4all.com/hardware/raspberry-pi/macosx-apple-pi-baker/) for Mac users.
    1.  There are many other free tools available to accomplish this depending on the system you’re using.
3. Once the Micro SD card has been formatted, copy the unzipped NOOBS folder onto the card. When this is finished, eject the card and remove it from your computer.
4. Insert the Micro SD card into the Raspberry Pi, boot it up, and complete the initial setup process.

#### _Initial Pi Setup_
1. Once the Pi has successfully booted up, open a terminal window and run the command ```hostname -I```. Take note of this IP and record it somewhere, as it will be needed in the next steps to access the pi remotely. 
2. Install Node.js and NodeRED by entering this command:  
```bash <(curl -sL https://raw.githubusercontent.com/node-red/raspbian-deb-package/master/resources/update-nodejs-and-nodered)```
3. Once this completes, run the command ``` sudo raspi-config```.
4. From this menu, enable SSH and the rPI camera, then choose the option to exit and reboot, installing any updates that may be offered.
5. From this point on, you can access your Raspberry Pi at the IP found in Step 1 of this process. To access the command line of your Pi use the command ```ssh pi@<your IP here>```. We will access the NodeRED flow GUI at the same IP address later.

### Step 2: Set Up IBM Cloud & Watson IoT Connections 

### Step 3: Import the NodeRed Flows

### Step 4: Edit the Necessary Nodes

### Step 5: Interact with MAX Models Through Dashboard