
SED Special Electronic Design
=============================

SED Limited society environment management

#. Remote access
#. Automations aimed at limiting consumption
#. Device automations override
#. Granular user privileges
#. Verification of consumpion of variable temporal arc
#. Hierarchical control between buildings
#. Hardware/plant

The electrical system globally exploits the use of contactors in bistable relay for the control of devices and not natively provided for a home automation system. The home automation control adapters have been added at a later time and positioned in parallel to preseistente plant, so as to read the status of the devices and also control the contactors. In this perspective, it wanted to show that it is possible to 'extend' a classic system with home automation controls, as well as to limit the planned set of activities and allow for retrofitting low costs.
The Easybox cards are therefore used to add a classic on the system advanced features, including:

#. Timing the ignition of the fan coil in order to ensure a homogeneous air conditioning of rooms
#. Timing the switching off of devices, so as to minimize the wastage from forgetfulness.
#. Collect data on the use of the devices so as to estimate the fuel consumption and the resulting savings, compared to the scenario of a classic system.

Software/Plugins
----------------

The system is run on a workstation WIN 7 Intel Core i3 and 4GB RAM; The same machine also houses a SQLSERVER 2008 server.

Plugins used for the current system
-----------------------------------

#. Easybox boards control
#. Harvester: storage of usage data on db
#. Twilight: events based on sunrise and sunset times
#. Chat: remote control, test controls and automation
#. Desktop Frontend