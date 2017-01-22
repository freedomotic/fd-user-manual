
Twilight - Sunset and sunrise alerts
====================================

**Description**: This plugin sends events related to Sunrise and Sunset time for the configured lat/long

**Type:**  - **Categories:** Utilities, Weather

**Development status:** Beta version

**Tested on:** All platforms

**Developer:** Matteo Mazzoni

Overview
--------
This plugin sends events related to Sunrise and Sunset time for the configured lat/long.


Configuration
-------------

In the file manifest you have to set only the following properties.

.. csv-table:: Parameters
   :header: "Parameter", "Meaning"
   :widths: 10, 10
   
   "lat","latitude"
   "log","longitude"

Events are populated with the following properties

.. csv-table:: Event properties
   :header: "Property", "Meaning", "Values"
   :widths: 15, 30, 30

   "isSunrise","sunset happened a few seconds ago","true or false"
   "isSunset","sunset happened a few seconds ago","true or false"
   "beforeSunset","minutes before the sun sets","integer"
   "afterSunset","minutes after the sun sets","integer"
   "beforeSunrise","minutes before the sun rises","integer"
   "afterSunrise","minutes after the sun rose","integer"
   