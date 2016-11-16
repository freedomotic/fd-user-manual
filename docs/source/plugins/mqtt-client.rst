
MQTT Client
===========

**Description**: A client for MQTT (MQ Telemetry Transport). It can be consider as a template for plugins based on this protocol

**Type:** Driver  - **Categories:** Automation Protocols, IoT

**Development status:** Prototype

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------
This plugin is a client for MQTT protocol.

Configuration
-------------
You can customize the plugin according to your needs.

Follow these steps:

1. open mqtt-client-manifest.xml and change at least the properties

   #. **broker-url:** ip address of MQTT broker
   #. **topic(s):** the topic(s) to subscribe in the <tuples></tuples> section
   #. other properties can be modified if needed (for example authentication with userid and password)
