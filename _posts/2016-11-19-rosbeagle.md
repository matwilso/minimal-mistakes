---
layout: post
title: "Installing ROS Kinetic on a Beaglebone Green Wireless"
date: 2016-11-19
---
## Intro
I installed ROS Kinetic on a Beaglebone Green for a [little robot I am making](https://github.com/matwilso/beaglebot).  I first tried to install Ubuntu on the Beaglebone, but I couldn't get the WiFi to work.  After hours of trying, I found that [the Ubuntu image]((https://rcn-ee.com/rootfs/bb.org/testing/2016-12-27/)) I was trying didn't have WiFi support (as of 2016).  I then had to switch to Debian.


## How to install Debian or Ubuntu
Follow the instructions for [Debian](http://elinux.org/BeagleBoardDebian#Flasher) or [Ubuntu](http://elinux.org/BeagleBoardUbuntu#Flasher).  Flasher section.  You will need a microSD card to boot the Beaglebone and an adapter to plug the microSD into a computer.  I believe there are other ways to boot the Beaglebone, but this is the easiest.


## Instructions to install ROS from source

Carefully follow the instructions on the ROS webpage.  Make sure to read the notes carefully so you don't miss an important step.

 First, [setup your sources to accept ROS packages][ros_install].  *Only do Steps 1.2, 1.3 and*
 `sudo apt-get update`

 Then, follow [the instructions on the ROS Wiki][ros_source] for installing from source.

## Building
Building your ROS install takes a __long__ time and might on the first fail a few times.  Be patient and keep trying.  When I built, it kept failing but I kept getting a little farther into the build process each time until it finally worked.  Just keep trying the same thing and expect different results.  What's Einstein's definition of insanity?  Anyway, if you keep seeing the same error message, search the internet.






## Thanks




[variants]: http://www.ros.org/reps/rep-0131.html#variants
[ubuntu]: http://elinux.org/BeagleBoardUbuntu#eMMC:_BeagleBone_Black.2FGreen
[deb]:http://elinux.org/BeagleBoardDebian#eMMC:_BeagleBone_Black.2FGreen
[ros_install]: http://wiki.ros.org/kinetic/Installation/Ubuntu
[ros_source]: http://wiki.ros.org/kinetic/Installation/Source
