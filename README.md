# Underwater-ROV
## Table of Contents
* [About](#About)
* [Overview](#Overview)
  * [Lateral Control](<#Lateral Control>)
  * [Depth Control](<#Depth Control>)
  * [Hull/Configuration](<#Hull/Configuration>)
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

After reviewing all of these propulsion configurations, I decided to use the first configuration with two motors. This is because for this ROV a key part of the goal is to keep down cost and complexity. To achieve this I was able to find a dual-motor brushed ESC that included the motors, shafts, and propellers which can be found here: https://www.amazon.com/dp/B0BYSG6JR1. This product is designed for RC boats but with the proper construction, this should still work for the ROV. The main thing to consider is how to seal the shaft, the product that I am using comes with tubes that can be used as a stuffing box which is how I will be waterproofing the shaft. This works to waterproof a shaft for a boat but the ROV will be at depth which will put pressure on the seal and could cause leaking. To avoid this I will also be using O-rings which should increase the ability of the shaft to seal under pressure. But there is still a chance of leaking, so the motors will be placed in two isolated nacelles so that even if the seal leaks all of the electronics will be isolated from the leak so the affect is minimized.

#### Depth Control
#### Hull/Configuration
#### Power
#### Communication
#### Video
