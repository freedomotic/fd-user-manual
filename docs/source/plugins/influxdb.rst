InfluxDB Persistence
====================

**Description**: Time series persistence on InfluxDB

**Type:** Driver - **Categories:** Utilities 

**Development status:** Prototype

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------
This plugin is intended to store data into an InfluxDB database.
It collects all things behaviors and values in the form of time series so data can be 
analyzed and used to create charts.

Configuration
-------------
First of all you need a running instance of InfluxDB and you have to set the connection parameters
into the manifest file.
If the authentication is enabled username and password are required.


