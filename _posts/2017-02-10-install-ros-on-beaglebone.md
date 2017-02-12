---
title: "Installing ROS Kinetic with OpenCV on a Beaglebone Green Wireless"
date: 2017-02-10
excerpt: Install ROS Kinetic on Beaglebone Green Ubuntu 16.04 Xenial, wifi enabled.
category: "ROS"
---
## Intro
This post shows how to install ROS Kinetic with OpenCV on the Beaglebone Green Wireless (BBGW) with Ubuntu 16.04. Most instructions should work for other Beaglebone variants.

I have tried installing ROS on Debian, but ROS doesn't build a Debian armhf, so you have to install from source.  When I tried compiling the source, I started getting internal compiler errors for some of the ROS OpenCV packages.  I reckon the ROS base would compile fine, but I have not tried that.  See the instructions for [installing from source][ros_source].

## How to install Debian or Ubuntu
I highly recommend using a microSD card for your Beaglebone.  You will likely run out of storage otherwise.

Follow the instructions here to install [Ubuntu](http://elinux.org/BeagleBoardUbuntu#raw_microSD_img).


## Setting up WiFi on BBGW Ubuntu
The wifi setup is pretty buggy for Ubuntu.  I got it to work by messing around in connman.  Try this:

``` bash
sudo connamnctl
# inside connman. Some of these commands may be unnecessary, but they worked for me.
enable wifi
scan wifi
agent on
scan wifi
tether wifi on
scan wifi
tether wifi off
disable wifi
scan wifi
enable wifi
scan wifi
services
```
You should get a list of WiFi and be able to recognize your SSID.

The next step is to enter `connect wifi_*`, replacing * with your own info.  After that, wait a minute and it will prompt you for a password.  Enter that, and you should see `Connected wifi_*`.  You are good to go.  Exit connman and try `ping 8.8.8.8`.  If it didn't work, try Googling the issue.

If it still doesn't work, checkout [this forum](https://groups.google.com/forum/#!starred/beagleboard/2cSM3FGjflM) for updates.

After that, you should be good to go.




# Install ROS Kinetic
Follow the instructions on the [ROS wiki][ros_install].


I have listed the commands here, but if you have any trouble, head to the ROS wiki.
<script src="https://gist.github.com/matwilso/9eca3cda4248c62ffcfd4ec8c9cf0a65.js"></script>








[variants]: http://www.ros.org/reps/rep-0131.html#variants
[ubuntu]: http://elinux.org/BeagleBoardUbuntu#eMMC:_BeagleBone_Black.2FGreen
[deb]:http://elinux.org/BeagleBoardDebian#eMMC:_BeagleBone_Black.2FGreen
[ros_install]: http://wiki.ros.org/kinetic/Installation/Ubuntu
[ros_source]: http://wiki.ros.org/kinetic/Installation/Source
