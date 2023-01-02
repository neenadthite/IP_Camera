Hi!!!! Bonjour!!!!

We have a plethora of CCTV's, home survellience cameras in the market. Many provide encrypted service. However, still data privacy issue persisits.
The special feature of this project is that the video streaming can only be accessed if the viewer device is in the same network.
The logistics used and setps involved in this are mentioned below.
Requirements:
Hardware: Raspberry Pi 3 (use can use Pi zero etc.), External Webcam (Pi camera can also be used), SD card, Laptop
Software: Raspbian OS, Motion package
Knowledge: You should be able to Flash the Pi OS, and enter inputs to the Pi by directly accessing the OS Graphical UI or through SSH.

Step 1:
Install Raspbian OS on SD card and Insert the card into Raspberry Pi. Connect to a WiFi Router or Access Point. Connect a webcam or Pi camera to the Pi.

Step 2:
Install Motion package using 
sudo apt-get install motion 

Step 3:
sudo nano /etc/motion/motion.conf ' and press enter.

Then you have to change some settings in the .conf file. It might be difficult sometimes to find the settings but use 'ctrl + w' to find it. So follow the steps:

Make sure 'daemon' is ON.
Set 'framerate' anywhere in between 1000 to 1500.
Keep 'Stream_port' to 8081.
'Stream_quality' should be 100.
Change 'Stream_localhost' to OFF.
Change 'webcontrol_localhost' to OFF.
Set 'quality' to 100.
Set 'width' & 'height' to 640 & 480.
Set 'post_capture' to 5.
Press ctrl + x to exit. Type y to save and enter to conform.
Again type in the command 'sudo nano /etc/default/motion ' and press enter.

Step 4:
Set 'start_motion_daemon' to yes. Save and exit.

Step 5:
First of all you have to restart the motion software. To do it type in the command 'sudo service motion restart' and press enter.

Step 6:
Again type in the command 'sudo motion' and press enter. Now your server is ready.

Step 7:
Now check the IP of raspberry Pi using 'ifconfig' and use the URL: http://ip_of_pi:8081 from other browser connected to the same router and view the live video footage seamlessly.
