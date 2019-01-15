# MAX & NodeRED on Raspberry Pi

This project contains two seperate NodeRED flows that can run on ony Raspberry Pi 3 with a camera, which will illustrate the use of using NodeRED and IoT devices to interact with Deep Learning Models from the Model Asset eXchange.


## Pre-requisites:
1. Raspberry Pi
2. Micro SD Card (8GB or larger recommended)
3. Raspberry Pi Camera

## Table of Contents

0. Run MAX Models on your Local Computer
   
1. Set Up The Raspberry Pi

2. Import the NodeRed Flows

3. Edit the Necessary Nodes

4. Interact with MAX Models Through Dashboard

——————————

### Step 0: Run MAX Models on your local computer
1. You can start the MAX Models needed for this project on you local computer with Docker.
2. To start the `MAX Image Caption Generator` on `Port 5000` run the command `docker run -it -p 5000:5000 codait/max-image-caption-generator`.
3. To start the `MAX Facial Recognizer` on `Port 5555` run the command `docker run -it -p 5555:5000 codait/max-facial-recognizer`.
4. To start the `MAX Audio Classifier` on `Port 7777` run the command `docker run -it -p 7777:5000 codait/max-audio-classifier`.

### Step 1: Set Up The Raspberry Pi

#### _If you are starting with a brand new Raspberry Pi, follow these steps to install Raspbian (your Operating System)._
1. Download the latest version of Raspbian at [this link](https://downloads.raspberrypi.org/raspbian_latest).
2. To create a bootable Micro SD, you'll need something to burn the image with. The free software [ApplePi Baker](https://www.tweaking4all.com/hardware/raspberry-pi/macosx-apple-pi-baker/) for Mac can accomplish this with the .zip file from above and the 'Restore Backup' button. (There are other free tools available to accomplish this for users on other types of systems.)
3. Once the Micro SD card is ready, remove it from your computer and insert it into the Raspberry Pi.
4. Connect the Pi to a display and power to complete the initial setup process. This involves setting a time zone, a root password, and connecting to your network.

#### _Initial Pi Setup_
1. Once the Pi has successfully booted up, open a terminal window and run the command ```hostname -I```. Take note of this IP and record it somewhere, as it will be needed in the next steps to access the pi via SSH. 
2. Run the command ```sudo raspi-config```.
3. From the 'Interfacing Options' menu, enable SSH and the camera, then choose 'Finish' to exit and reboot.
4. From this point on, you can access and control your Raspberry Pi with the IP address found in Step 1 of this process. To do this, use the command ```ssh pi@<your IP here>``` from a computer on the same network. We will access the NodeRED flow GUI at the same IP address later.
5. Install Node.js and NodeRED by entering this command:  
```
bash <(curl -sL https://raw.githubusercontent.com/node-red/raspbian-deb-package/master/resources/update-nodejs-and-nodered)
```
6. Once this completes, set NodeRED to initialize on startup with ```sudo systemctl enable nodered.service```.

### Step 2: Import the NodeRed Flows
1. Navigate to the home directory of your Raspberry Pi in a terminal window with the command `cd ~`
2. Clone this repository to your Pi with `git clone <path_to_repo>`
3. Copy the contents of the new directory to your NodeRED directory with `cp -r repo_name/* .node-red`
4. Open a Web Browser on your computer and navigate to `http://<raspi_ip_address>:1880` to verify the flows have been loaded.
### Step 4: Edit the Necessary Nodes
1. Open the NodeRED Web interface at `http://<raspi_ip_address>:1880`.
2. From the row of tabs at the top of your flows, select "Camera Settings/ Troubleshooting"
3. Click the button on the leftmost node labeled "Click to Capture Image". This will display the output of your Raspberry Pi's Camera to verify the settings are correct. If the image is not showing up, or if it needs to be flipped horizontally or vertically, double click the Camera Node to make these adjustments. If you make changes, you can copy this node with `Ctrl-C` and paste it with `Ctrl-V` in the other flows as needed.
4. On the tabs for flows "Image Caption Generator" and "Facial Recognizer", click the MAX Model node of the same name. Within these nodes, we will need to add a "Service" for each model by clicking the pencil icon and supplying the address (and port) for our MAX model.
   
### Step 5: Interact with MAX Models Through Dashboard
1. To view the dashboard for your Raspberry Pi, navigate to `http://<raspi_ip_address>:1880/ui` in your web browser.
2. By default, you should see the Image Caption Generator dashboard. Click on the "Capture Image" button to capture an image on your Raspberry Pi and send it to the appropriate MAX model, displaying the results on this page.
3. To switch to the Facial Recognizer tab, select the menu icon on the left side of the navbar and choose it from the list.
4. Click the "Capture Image" button on this page to similarly capture a photo on the Pi and submit it to the MAX Model for prediction.