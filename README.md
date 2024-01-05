# Underwater-ROV
## Table of Contents
* [About](#About)
* [Overview](#Overview)
  * [Lateral Control](<#Lateral-Control>)
  * [Depth Control](<#Depth-Control>)
  * [Hull/Configuration](<#HullConfiguration>)
  * [Power](<#Power>)
  * [Communication](<#Communication>)
  * [Video](<#Video>)
* [Improvements](#Improvements)

## About
The goal of this project is to create a fully functional underwater ROV without spending a lot of money. This means that the ROV should be able to move freely horizontally and vertically throughout a body of water and should be able to send and record live video.

## Overview
In order to complete the goal several components must be considered: lateral control, depth control, hull/configuration, power, communication, and video.
#### Lateral Control
To move freely in a body of water most ROVs use thrusters in a variety of configurations for maneuverability. There are three commonly used configurations for ROV propulsion each of which has its own influence on the power, electronics, and number of thrusters needed to function. The first configuration utilizes two thrusters in the same orientation situated on each side of the ROV as shown below.
![two thruster propulsion](https://github.com/JoshCircenis/Underwater-ROV/assets/98178221/8099c511-6530-46c1-86c4-4f44a336e865) ![two thruster propulsion maneuverability](https://github.com/JoshCircenis/Underwater-ROV/assets/98178221/9ca38ea4-d64d-4434-b501-fdb66d61c851)

This configuration uses differential control for turning and drives both thrusters at the same level for forward and reverse. The benefit of this propulsion configuration is that it is very simple in terms of thrusters, electronics, and power. The main drawback is that this configuration is less maneuverable and generally less powerful than other configurations. To improve maneuverability the thrusters can be installed at an angle, this improves the turning ability but can reduce the forward and reverse thrust.

The second configuration utilizes three to four thrusters where two are placed in the same configuration as the previous, but additional thrusters are placed perpendicular to the first set as shown below.

![three thruster](https://github.com/JoshCircenis/Underwater-ROV/assets/98178221/2091a08d-ef15-451f-8c5d-68c65e38adff) ![four thruster](https://github.com/JoshCircenis/Underwater-ROV/assets/98178221/00e6871d-880b-4375-a48e-ec2cab729856)

This configuration requires more power and electronics because there are more thrusters but it is more powerful and maneuverable than the previous configuration.

The third configuration utilizes four thrusters which are all placed at an angle around the ROV as shown below.
![four thruster angled](https://github.com/JoshCircenis/Underwater-ROV/assets/98178221/4ebe9433-47d5-4de4-99e2-ec8ab5a0ebc8)

This configuration is a balance between having full maneuverability and power. In this configuration, depending on the mixing, all motors can be used for both forward and reverse thrust and for turning. However, this configuration is more complicated.

After reviewing all of these propulsion configurations, I decided to use the first configuration with two motors. This is because for this ROV a key part of the goal is to keep down cost and complexity. To achieve this I was able to find a dual-motor brushed ESC that included the motors, shafts, and propellers. This product is designed for RC boats but with the proper construction, this should still work for the ROV. The main thing to consider is how to seal the shaft, the product that I am using comes with tubes that can be used as a stuffing box which is how I will be waterproofing the shaft. This works to waterproof a shaft for a boat but the ROV will be at depth which will put pressure on the seal and could cause leaking. To avoid this I will also be using O-rings which should increase the ability of the shaft to seal under pressure. But there is still a chance of leaking, so the motors will be placed in two isolated nacelles so that even if the seal leaks all of the electronics will be isolated from the leak so the damage is minimized.

#### Depth Control
The most common method of depth control in an ROV is using vertical thrusters on a neutrally buoyant ROV. In this way, the thruster can be driven forward or reverse to control the depth of the ROV. However, another way to do this is with variable weight. In this method, the ROV would alter its weight to be greater than that of the water that it displaces to dive and lighter than that of the water that it displaces to rise. I decided to utilize the second method and incorporate ballast tanks into the ROV. This is because I believed that it would be possible to design the tanks such that they were very cheap and simple to build, install, and use and it would allow for a more streamlined design. I was originally planning on using linear actuators to pull and push 50mL syringes which would pull in and push out water to change the weight. However, after doing some research into different designs I found that it would be cheaper and possibly more accurate to instead convert a regular 9g servo into a linear servo which could accurately position the syringe. To do this I swapped the motor in a 9g servo with a motor that operates on a similar voltage but is heavily geared to handle the load that it would experience when moving the syringe. This motor was coupled to a lead screw which would pull and push a captive nut in a custom 3D-printed syringe plunger which also moved a linear potentiometer to tell the servo its current position. Additionally, two 10k rotational potentiometers were included to adjust and fine-tune the travel of the syringe, and two thrust bearings were included on each side of the shaft coupling to transfer the load from the motor to the 3D-print which improves operation. This video shows the linear servo moving the syringe and automatically slowing down and stopping, the movement of the motor in the clip is due to not adjusting the shaft coupler set screws evenly and it won't occur in the final ROV. 

https://github.com/JoshCircenis/Underwater-ROV/assets/98178221/16f27a67-2fc3-4133-86e2-2686d9d1983a



#### Hull/Configuration
#### Power
#### Communication
#### Video
