# OpenFPV
OpenFPV is a DIY digital FPV system for UAVs that leverages low-cost IP camera modules running custom OpenIPC firmware, paired with high-power WiFi adapters to stream video over long distances on the 5 GHz ISM band. This project aims to build a semi-long-range (up to ~5 km) FPV system that's modular, affordable, and hackable.

![camera](https://ae-pic-a1.aliexpress-media.com/kf/S8692bf1c5a604fc3b379987b254260a5f.png_960x960.png)


## Project goals

- mid range (5-6 km)
- reliable
- open source!
- cheap

## System Overview

### Airside (UAV)

| Component            | Description                                      |
|----------------------|--------------------------------------------------|
| Camera               | SSC338Q SoC + IMX415 1080p module                |
| WiFi Adapter         | BL-M8812EU2 (RTL8812EU, ~29 dBm TX power)        |
| Custom PCB           | Power regulation (LiPo to 5V), heatsink + fan    |
| Antennas             | 2× 5 dBi stubby antennas                         |
| Firmware             | OpenIPC (RTSP output)                            |

---

### Ground Station

| Component            | Description                                      |
|----------------------|--------------------------------------------------|
| WiFi Adapter         | BL-R8812AF1 (RTL8812AU)                          |
| Antennas             | 13 dBi omni + 23 dBi panel (MIMO diversity)      |
| Custom PCB           | Powered via USB OTG, ESD protection, USB-C       |
| Mobile Device        | Android phone with PixelPilot |
| Software             | H.264 decoding via PixelPilot                    |

---


# BOM

|Category   |Component                          |Qty|Unit Cost (USD)|Total Cost|link                                                  |
|-----------|-----------------------------------|---|---------------|----------|------------------------------------------------------|
|Camera     |SSC338Q + IMX415 camera module     |1  |$30.00         |$30.00    |https://www.aliexpress.com/item/1005007899575234.html |
|Antenna    |5 dBi stubby antennas (SMA)        |2  |$2.50          |$5.00     |https://www.aliexpress.com/item/1005004388721764.html |
|WiFi Module|BL-M8812EU2 (RTL8812EU)            |1  |$11.00         |$11.00    |https://www.aliexpress.com/item/1005007723850436.html |
|Cooling    |Heatsink + 5V micro fan            |1  |               |          |already have                                          |
|PCB        |Airside custom PCB                 |1  |$20.00         |$20.00    |jlcpcb + components                                   |
|           |                                   |   |               |          |                                                      |
|WiFi Module|BL-R8812AF1 (RTL8812AU)            |1  |$11.52         |$11.52    |https://www.aliexpress.com/item/1005006486060233.html |
|Antenna    |13 dBi omni + 23 dBi panel antennas|2  |$17.00 + 2     |$19.00    |https://www.aliexpress.com/item/1005005559736986.html?|
|PCB        |Groundstation custom PCB           |1  |$15.00         |$15.00    |jlcpcb + components                                   |
|           |                                   |   |               |          |                                                      |
|Misc.      |Solder, headers, standoffs, extras |   |$10.00         |$10.00    |                                                      |
|           |                                   |   |               |$121.52   |                                                      |
