# Self-driving_fire-truck

This project was created by undergraduates attending Suwon, Kyungil Univ. for 21th 2023embedded sw contest

## Overview
This project is the source code for self-Driving fire Truck. This code implements motion control of a 1:8 scale car, including move by joystick or autonomatically. Supporting libraries provide additional capabilities, such as object detection by camera to provide accident. The software is implemented on a Jetson Nano running Ubuntu 18.04 with ROS Melodic installed.

The software is composed of Arduino, C++ and Python nodes in a ROS framework.

  <img src = https://user-images.githubusercontent.com/65767592/234626692-46028ea9-1cc3-433e-b677-3cb65b43b86f.PNG  >

                                         
### Software settings
```
* Jetpack 4.5.1 Darknet yoloV4 ROS Melodic
* OpenCV 4.5.1 CUDA 10.0 CUDNN 8.0 Tensorflow 2.5.0
```
I used compact command to install ROS melodic written by zeta(https://github.com/zeta0707/installROS.git)


## Self Driving

Self-driving is for patrol where being fired. We used python to send goal for ROS SLAM. Cartogrphor is also used to obtain maps.

Here's the map and the navigation we got

<img src = https://user-images.githubusercontent.com/65767592/235427299-fb32638c-17a3-4ed7-bec6-ed2805b5473b.gif  width="450" height="350"  align="left">
<img src = https://user-images.githubusercontent.com/65767592/235427736-1006aaee-7dc9-47ca-af52-d081794774f0.jpg   width="370" height="350" align="right">


## Fire detection

Fire detection of this project is for fire fighting purposes. So we considered a way to accurately detect fire through two sensors and then find the coordinate value of the fire.

The fire detection system determines that the fire was truly detected when object detection by the camera sensor and fire wavelength detection by the flame sensor were performed at the same time.

A flame sensor is detect a specific wavelength generated only fire.(185nm~260nm) It can detect up to flame of in front 0.5m

### Object Detection

The project contains object detection by using darknet yoloV4-tiny. 
I made customize weight file by machine learning.  
I extracted the coordinate value of fire by extracting the coordinate of the bounding box drawn when detecting fire.
And i modified batch and subdivision for Jsons capability.






