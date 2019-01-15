# MAX & NodeRED on Raspberry Pi

This project contains two seperate NodeRED flows that can run on ony Raspberry Pi 3 with a camera, which will illustrate the use of using NodeRED and IoT devices to interact with Deep Learning Models from the Model Asset eXchange.


## Pre-requisites:
1. Raspberry Pi
2. Micro SD Card (8GB or larger recommended)
3. Raspberry Pi Camera


## Table of Contents

1. Set Up The Raspberry Pi

3. Import the NodeRed Flows

4. Edit the Necessary Nodes

5. Interact with MAX Models Through Dashboard

——————————

### Step 1: Set Up The Raspberry Pi

#### _If you are starting with a brand new Raspberry Pi, follow these steps to install Raspbian (your Operating System)._
1. Download the latest version of Raspbian at [this link](https://downloads.raspberrypi.org/raspbian_latest).
2. To create a bootable Micro SD, you'll need somethings to burn the image with. The free software [ApplePi Baker](https://www.tweaking4all.com/hardware/raspberry-pi/macosx-apple-pi-baker/) for Mac can accomplish this with the .zip file from above and the 'Restore Backup' button. (There are other free tools available to accomplish this fpr users on other types of systems.)
3. Once the Micro SD card is ready, remove it from your computer and insert it into the Raspberry Pi.
4. Connect to a display (for now) and power on the Pi to complete the initial setup process.

#### _Initial Pi Setup_
2. Once the Pi has successfully booted up, open a terminal window and run the command ```hostname -I```. Take note of this IP and record it somewhere, as it will be needed in the next steps to access the pi via SSH. 
3. Install Node.js and NodeRED by entering this command:  
```
bash <(curl -sL https://raw.githubusercontent.com/node-red/raspbian-deb-package/master/resources/update-nodejs-and-nodered)
```
3. Once this completes, run the command ``` sudo raspi-config```.
4. From this menu, enable SSH and the rPI camera, then choose the option to exit and reboot, installing any updates that may be offered.
5. From this point on, you can access your Raspberry Pi at the IP found in Step 1 of this process. To access the command line of your Pi use the command ```ssh pi@<your IP here>```. We will access the NodeRED flow GUI at the same IP address later.

### Step 3: Import the NodeRed Flows

### Step 4: Edit the Necessary Nodes

### Step 5: Interact with MAX Models Through Dashboard
