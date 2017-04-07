Z-Wave
======

**Description**: This plugin allows interfacing with zwave-powered devices

**Type:** Driver - **Categories:** Automation protocols 

**Development status:** Proof of Concept

**Tested on:** All platforms

**Developer:** Matteo Mazzoni

Overview
--------
This plugin uses a usb serial-to-zwave adapter (or every serial to zwave port) and an ad-hoc library (Zwave4j) to interface with devices. Requires Java 8 or above. 

Configuration
-------------

Supported adapters
------------------

Not all this devices are tested, but they are supposed to work:

* Tricklestar (USB)
* ACT ZCS101 (Serial port)
* Z-troller (Serial port)
* Aeon ZStick (USB)
* Seluxit ViaSens 100 (USB)
* Z-Wave.Me Z-Stick (USB)

Supported devices
-----------------

At a first stage will be supported Lights and Thermostats devices. Many other devices will be added during the beta phase. The following list reports all tested devices

**SENSORS**

* Aeon Labs Multisensor DSB05-ZWEU

**ACTUATORS**