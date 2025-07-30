---
title: "OpenEyePC"
author: "Burger"
description: "OpenIPC cameras for UAVs"
created_at: "2025-07-20"
---


# OpenEyePC FPV

# July 20'th 
Project inception:
Goals for this project:
- make a good digital FPV system for UAVs 
	- that's cheap
	- reliable
	- reletively long range
	- ISM bands
	- works

so I decided to use cheap IP cameras with custom OpenIPC firmware and custom PCB backboards to add wireless adapters.

This took some research, I initally came across it while making my FlyQ fixed wing, I found it i quite interesting when i first came across it.

## Why OpenIPC?
OpenIPC stood out to me because it's flexible, open-source, and has a surprisingly active community. Most people use it for home security setups, but the idea of using it for airborne FPV was too tempting.

These cheap IP cameras (often based on HiSilicon or XM chips) have decent imaging hardware for the price and with OpenIPC, you unlock full control over streaming, resolution, bitrate, and more. Combine that with some basic Linux tinkering, and suddenly you have a DIY digital FPV system. I wasn't the first to invent this, they already are working on firmware, I talked with some involved in with the community directly to get some more idea.

## Why? 
While researching for my drone project, I came across various FPV system, some analog, some digital, some cheap, some rather expensive. I had initially choosen an Analog FPV system, a Runcam cycling camera (lol) with a speedybee VTX, but I want something with superior range and customizable.

time spent: 3 hours

# July 21'st
Working more on this, this system will have the these minimum technical capabilities:
- Camera
	- Camera Sensor: IMX415 (as heard from the community)
	- Minimum resolution: 1080p 
	- Min. FPS: 30
	- Latency: sub 100 ms
	- Chip: SSC338Q (also recommended by devs)
- Ground Station
	- Fast H.264 decode
	- MIMO Antenna capabilities for better reception

Based on this, let's refine and make this work.

For the Camera, I have choosen a IP camera module I found on aliexpress which falls within the criteria of selection, it's actually great, cheaper than most since I am buying a mass produced IP camera module without even the housing. 
This camera would be connected to a daughter board that'd connect it with the wifi module and power it all.

For the Groundstation,, I will use a custom PCB capable of being plugged into a phone that would recognize it as a wifi adaptor and with PixelPilot work as a FPV monitor!

Camera:
![](https://ae-pic-a1.aliexpress-media.com/kf/S8692bf1c5a604fc3b379987b254260a5f.png_960x960.png)
This is a SigmaMaster SSC338Q IMX415 Module for the camera.

For the Camera, it'll use a IMX415 sensor as mentioned.

I read through the spec sheet for the SSC338Q chip and it's kinda awesome, it can do a lot and is prefect indeed. If you want to take a look, [you can](https://www.sigmastarsemi.com/uploadfile/file/20220419/20220419031720_62035.pdf).

For the lens, it'll use a 3.6 mm lens, which I feel would be ok for this purpose.

For the Airside tx, I am thinking of using a this BL-M8812EU2 from LB Link, which is based on the RTL8812EU module, it's a great module because it supports upto 29 dBm of output power while being very cheap (~$10)
![](https://ae-pic-a1.aliexpress-media.com/kf/S2b2c990a7166492caf2a3e1a06e23abfY.jpg_960x960q75.jpg_.avif)
I'd need to make a custom PCB to house this board and all the components that'll be required to power it (and the camera). Will probably add a heatsink to cool it down.

For the Groundstation side, I'll just use a LB-LINK BL-R8812AF1 board on a custom pcb to connect with a phone to interface with Pixelpilot. Also reletively cheap at around ~$10
![image](https://raw.githubusercontent.com/OpenIPC/docs/refs/heads/main/src/assets/images/bl-r8812af1-top.png)
This is based on the RTL8812AU, an old chip that's time tested.

time spent: 4 hours