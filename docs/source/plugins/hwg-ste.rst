
HWg-STE Ethernet thermometer
============================

**Description**: This plugin reads values from an ethernet thermometer by HW-group.com

**Type:** Driver - **Categories:** 

**Development status:** Stable Release

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------
This plugin reads values from an ethernet thermometer by HW-group.com. You can connect to it up to two sensors of temperature and humidity. Indoor/outdoor sensors available. Even temperature sensor with flat cable for temperature monitoring in the fridges. More details at http://www.hw-group.com/products/HWg-STE/STE_ip_temperature_sensor_en.html

It works sending periodically **SNMP** (Simple Network Management Protocol) request to the device using the **OID** (Object Identifier) specified by the manufacturer (http://ste.hwg.cz/HWg-STE_OID.txt).

Configuration
-------------

All the configuration parameters are included in the hwgste-manifest.xml file. You can use it without any changes.

Each thermometer data are included in a ``<tuple></tuple>`` block where you need to specify:

* ip address of the device
* number of sensors (2 by default) 

How to read temperature
-----------------------
Add a thermometer object to your Freedomotic environment:

* Right click on the thermometer in the environment to show its configuration panel
* Change the property "protocol" to "hwgste"
* Change the property "address" to a string composed of **HWG-STE-ADDRESS:SENSOR-ID**  where **HWG-STE-ADDRESS** is the ip address of your device and **SENSOR-ID** is the id of your monitoring sensor. An example address can be **ste.hwg.cz:215**. The plugin is able to read any relay status change and update the object one.
* Under "temperature" (in **Data Sources**) select from the list ``HWg-STE reads temperature``.
