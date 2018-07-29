# Ros Drone Project
Central page for all of my drone related stuff. This project documents my attempt to build a fully workable drone using the Robotic Operating System from scratch. Much like the [BARC-project](http://www.barc-project.com/), a low cost robotics platform is an essential part of lowering the entry barrier for robotics. This platform now exists for RC cars, but I have not seen drones running on ROS that are easily available just yet. Few research project on autonomous aircraft ever make it out of simulation or highly controlled lab rooms, and I think this could help those projects make that transition.
## CAD files
All CAD files can be found in [this](/CADs) directory, including an assembly with all the parts. The frame is intended to be CNC-ed, and an Adobe Illustrator vector file is included so you can easily go and laser-cut or water-jet the frame from a piece of plywood or metal.

## Bill of Materials
A sparse bill of materials is included [here](/BOM). I had some parts lying around that I just used, and so I didn't include them in my Bill of Materials. You will still need to buy a: LiPo-battery with a charger, a 5-volt regulator, and some cables to make a wiring harness from to connect everything together. You could buy a ton of connector cables and adaptors, but I prefer to just solder everything together myself. 

|Part|Approx Price|
|---|---|
|Raspberry Pi 3+ with SD card | $50|
|Motors and ESC's| $70|
|Arduino nano with shield| $20|
|Propellors|$15|
|IMU|$30|
|Frame materials (plywood)| $15|
|*Total*|$200|

## Code Setup
You will need to install an operating system on the Raspberry Pi and subsequently install ROS on it. You can install ROS on Raspbian, the OS created by Raspberry pi, but the setup is a bit of a pain in the ass. I have found it easier to install Ubuntu Xenial image with ROS pre-installed on it. You can find instructions for that [here](https://downloads.ubiquityrobotics.com/pi.html). 

To use my nodes, you will need to clone my [workspace](https://github.com/GoldeneyeRohan/RDRONE). If you are not familiar with ROS (or git), here is how to do this:

`cd /directory-where-you-want-your-workspace`

`mkdir catkin_ws #some workspace directory name`

`cd catkin_ws`

`mkdir src`

`catkin_make #skip all the steps up to here if you just want to plop into existing ws`

`cd src`

`git clone https://github.com/GoldeneyeRohan/RDRONE.git`

`cd ..`

`catkin_make`
Then source the workspace either by running this (one time use):
`source devel/setup.bash`
OR (always load it into shell): 
`echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc`


