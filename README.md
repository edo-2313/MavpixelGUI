# MavpixelGUI

## Windows Installer - [Download](https://github.com/prickle/MavpixelGUI/releases)

MavpixelGUI is the Windows configurator application for Mavpixel.

Mavpixel brings Cleanflight-style LED strip functionality to the APM project.

Mavpixel is a LED strip controller designed as a companion for APM, Pixhawk and other Mavlink-compatible flight controllers. Based on simple, inexpensive hardware, Mavpixel is a well-featured complete LED lighting solution for larger UAVs.

For more information on the Mavpixel board including installation and wiring see the [Mavpixel Github](http://github.com/prickle/Mavpixel)

![MavpixelGUI main window](https://github.com/prickle/MavpixelGUI/raw/master/images/MavpixelGUI.jpg)

## Using MavpixelGUI

MavpixelGUI is provided with layout and controls familiar to users of [Cleanflight](http://github.com/cleanflight/cleanflight). It acts as a minimal ground station and can connect to any available serial or network port or through another ground station in either Mavlink or CLI mode as appropriate. It also includes a firmware flasher for preparing and keeping Mavpixel boards up to date.

Because Mavpixel is based on Cleanflight LED control, much of the [Cleanflight LED strip documentation](https://github.com/cleanflight/cleanflight/blob/master/docs/LedStrip.md) is quite relevant, including the CLI commands. This information can be used to provide a perspective on the LED control system used by Mavpixel and MavpixelGUI.

Note that changes made in the GUI are activated on the Mavpixel only after the Send button at the bottom of the window is pressed.

## Connecting to Mavpixel

MavpixelGUI can connect to Mavpixel in many ways, using existing channels or through new ones, either offline or while running.

Mavpixel has two serial ports, either of which can be used by MavpixelGUI directly. Connecting using the FTDI programmer gives quick offline access. A secondary configuration port is also available as described below.

When Mavpixel is connected to a vehicle the flight controller can forward it's messages over the Mavlink connection, allowing MavpixelGUI to connect through the flight controller's USB or network port. 

Mission Planner and other ground stations can also forward Mavlink messages to the network giving MavpixelGUI the ability to connect over the network, through a running ground station, back up to the vehicle, and on to a live Mavpixel for full remote configuration access. For more details see below.

## Connecting through Mission Planner

Connect Mission Planner to the vehicle in the usual way over USB, telemetry or any other preferred connection.

In MavpixelGUI select the UDP entry from the Port selector. Note the port (usually 14550). Click 'Connect' and leave MavpixelGUI waiting for the connection.

![MavpixelGUI Port Selector](https://github.com/prickle/MavpixelGUI/raw/master/images/MavpixelGUIUDP.jpg)

In Mission Planner, press <ctl> - f to bring up the hidden menu. 

![Mission Plnner hidden menu](https://github.com/prickle/MavpixelGUI/raw/master/images/MissionPlannerMirror.jpg)
 
Click 'Mavlink' to open Mission Planner's Mavlink mirror window. 
In this window, select 'UDP Client' and 115200, enable write access and click 'Connect'.

![Mission Planner UDP window](https://github.com/prickle/MavpixelGUI/raw/master/images/MissionPlannerUDP.jpg)
 
In the next window 'remote host' leave it as default 127.0.0.1 and click 'OK'.

![Mission Planner UDP Host](https://github.com/prickle/MavpixelGUI/raw/master/images/MissinPlannerHost.jpg)

In the next window 'remote Port' ensure the port number matches the port in MavpixelGUI and click 'OK'.

![Mission Planner UDP Port](https://github.com/prickle/MavpixelGUI/raw/master/images/MissinPlannerPort.jpg)

MavpixelGUI should now connect to the Mavpixel through Mission Planner. In this mode with heartbeats disabled Mavpixel messages are invisible to Mission Planner which is simply acting as a router.   

Note that configuring Mavpixel this way generates extra traffic on telemetry connections which could create problems in some circumstances. It is therefore not recommended to configure Mavpixels in flight. 

*More to come..*

## Acknowledgements

MavpixelGUI owes thanks to it's contributors. Most notably:

[Cleanflight](http://github.com/cleanflight/cleanflight) (LED strip window design) - Dominic Clifton, Petr Ledvina, Gaël James and many others.

[Mission Planner](http://github.com/ArduPilot/MissionPlanner) (Mavlink libraries and simpleexample.cs) - Michael Oborne.

[Serial Port Net](http://sourceforge.net/projects/serialportnet/) - Daniel Moth and Yuri Astrakhan.

[GraphicsExtension.cs](http://www.codeproject.com/Articles/38436/Extended-Graphics-Rounded-rectangles-Font-metrics) - Arun Reginald Zaheeruddin.

[AVRDude](http://www.nongnu.org/avrdude/) - Brian S. Dean.

[Alpanum.cs](http://www.davekoelle.com/) - Dominik Hurnaus

Apologies to any I may have forgotten or missed. If you belong here let me know.

This software is released under the open source GPL license. For more details, see LICENSE in the application directory.
