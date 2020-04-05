### Mavsdk in raspberry pi
All the installations are similar to that in PC but you will neet to source build mavsdk server and also download the appropriate arm image and replace the mavsdk server.
Refer to the attached pdf file for detailed steps or visit<a> https://discuss.px4.io/t/talking-to-a-px4-fmu-with-a-rpi-via-serial-nousb-ardunope/14119/4</a>

![](mavsdk.png)
As suggested download the mavsdk binary image specifically armv7 version
Ordered steps:
* Install mavsdk using source build as instructed:
* Download and replace mavsdk server using the armv7 version from <a>https://github.com/mavlink/MAVSDK/releases/tag/v0.23.0</a> or it is contained in this repo
* provide permission if needed chmod +x to mavsdk server
* add shebang line if it shows OS error #! /usr/bin/env python

<b> Note: Complete each step and be patient as build takes a lot of time</b>

Ref:
https://mavsdk.mavlink.io/develop/en/contributing/build.html
https://github.com/mavlink/MAVSDK-Python

