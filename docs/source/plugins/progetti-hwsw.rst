
ProgettiHw-Sw Ethernet Board v2
===============================

**Description**: Communicates with an ethernet relay board by ProgettiHw-Sw.

**Type:** Driver - **Categories:** Automation Protocols

**Development status:** Stable Release 

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------

With this plugin Freedomotic can communicate with an ethernet relay board by ProgettiHw-Sw.
These boards have from 8 up to 16 relays, an ethernet port and an integrated web server

Configuration
-------------

With this type of board you can control the powered behavior of any electric device in your environment, meaning you can turn on/off electric devices.

How to control a relay
----------------------

* Right click on the light object in the environment to show its configuration panel
* Change the property **protocol** to **phwswethv2**
* Change the property **address** to a string composed of **ALIAS:RELAY_NUMBER:TAG**  where **ALIAS** is the string set in the configuration file (phwswethv2-manifest.xml) to identify the board. **RELAY_NUMBER** is the relay used to control your device (from 1 to 16). **TAG** is one of the following string: **led** (for relays), **pot** (for analog inputs), **btn** (for digital inputs). For example **default:1:led** identifies the first relay on a board called **default**.
* Under **turn on** (in **Actions**) select the command called **Turn ON Relay on ProgettiHwSw Eth board**
* Under **turn off** (in **Actions**) select the command called **Turn OFF Relay on ProgettiHwSw Eth board**

The plugin is able to read any relay status change and update the object one.

* Under **powered** (in **Data Sources**) select the trigger called **ProgettiHwSwEthV2 reads a state change**.

Use cases
---------

* https://www.emmecilab.net/gestione-di-un-appartamento-con-freedomotic/ (in Italian)
