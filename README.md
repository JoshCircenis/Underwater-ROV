# Underwater-ROV
## Table of Contents
* [About](#About)
* [Overview](#Overview)
  * [Lateral Control](<#Lateral-Control>)
  * [Depth Control](<#Depth-Control>)
  * [Hull](<#Hull>)
  * [Communication](<#Communication>)
* [Improvements](#Improvements)

## About
The goal of this project is to create a fully functional underwater ROV without spending a lot of money. This means that the ROV should be able to move freely horizontally and vertically throughout a body of water and should be able to send and record live video.

## Overview

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

https://github.com/JoshCircenis/Underwater-ROV/assets/98178221/2553f830-2ba3-4c8f-8b04-3c350286e0a8

The final ROV will have two of these allowing for 50mL of water to be displaced. This solution cut down the cost and complexity a lot because each tank can simply be driven as a regular servo and the components used to create the tanks were inexpensive. Additionally, the ROV will have two of these tanks, one on each end, which will allow for pitch control by moving the center of mass of the ROV between the two tanks.

#### Hull
Many ROVs use a frame design where a PVC frame holds all of the components of the ROV. However, because of the motors that I am using, I decided to go for a more hydrodynamic and streamlined design to reduce drag. Additionally, I would like to minimize the amount of material necessary for the hull by reducing complexity. Because of this, I decided to use three feet of 4" schedule 40 PVC pipe to house everything except for the motors which will be in two smaller side nacelles as previously stated. This will keep down the cost and complexity while still creating a functional and pressure-resistant hull. Also, to improve footage recorded from the ROV the front will have a clear dome which will allow for a greater field of view for the cameras. Below is a 3D model that outlines the structure and is similar to how it should look once completed

![ROV](https://github.com/JoshCircenis/Underwater-ROV/assets/98178221/b1d3c77b-2ff8-4273-b0a5-bd9ef838b1e7)


#### Communication
To control the ROV I plan on using fs-i6 fs-ia6b an RC transmitter and receiver. But, 2.4 GHz which is the most common RC frequency only penetrates a few centimeters through water so just putting a receiver on the ROV won't work. It is possible to use a receiver and transmitter with lower frequencies but those cost more and I already had a Flysky FS-I6 transmitter and an FS-IA6B receiver. To get around this problem the ROV will have a tether to the surface of the water. For the tether, I am using 100 feet of CAT5 ethernet cable because it is easy to get and will have more than enough wires to control the ROV. The tether will connect to the ROV with an underwater ethernet port so that the tether and float can be disconnected when not in use or to swap tethers. The FS-IA6B has PPM capability which will encode all of the channels that the receiver has and send it over a single line through the tether to the ROV where it will be connected to a PPM decoder which has all of the necessary PWM ports for the motors and servos. Additionally, a video transmitter for FPV drones will be in the float and the video signal will run from the camera in the ROV through the tether to the float. This will provide live video for piloting the ROV and a GoPro or RunCam will also be on the ROV to record higher-quality footage that can be viewed later. With this setup, it is also necessary for the float and the ROV to each have their own onboard batteries to avoid losses in transmitting power over the tether. The float will have a 2s (7.4V) 900mAh lipo battery because it only has to support the RC receiver and the video transmitter and the ROV will have a 2s 4000mAh lipo battery to support all of the electronics on the ROV. Because of this, it is also necessary to connect the ground of the float and ROV using the tether because the signals being sent over the tether are ground-referenced.

Below is a photo of all of the components for both the ROV and the float laid out.

![IMG_3182](https://github.com/JoshCircenis/Underwater-ROV/assets/98178221/349a236f-55a3-46cc-8223-dbc40021fa7b)

## Improvements
Since this project has not been completed yet I am not sure about improvements that need to be made, but I am suspicious of the shaft seals and power. Because the motors that I am using are made for a boat that is smaller and has less drag I am concerned about the ROV being extremely slow. Also, I am planning on using a tube filled with grease that goes around the shaft with a tight tolerance to seal the drive shaft but this might not work at depth. It is not a huge issue if it leaks because the motors shouldn't break and they are completely isolated from the main tube so it won't damage the electronics. However, I don't want it to leak and I have some preemptive ideas that could fix it, such as 3D printing a grease trap that incorporates several O-rings or adding a flexible membrane to the nacelle to equalize pressure during the dive. But I will first have to wait till the first test to see if the original plan works before implementing these.
