
Twilight - Sunset and sunrise alerts
====================================

**Description**: This plugin sends events related to Sunrise and Sunset time for the configured latitude/longitude.

**Type:**  - **Categories:** Utilities, Weather

**Development status:** Beta version

**Tested on:** All platforms

**Developer:** Matteo Mazzoni

Overview
--------
This plugin sends events related to Sunrise and Sunset time for the configured latitude/longitude. It's based on OpenWeatherMap 
and EarthTools providers.


Configuration
-------------

In the manifest file you have to set the following properties:

.. csv-table:: Parameters
   :header: "Parameter", "Meaning"
   :widths: 10, 10
   
   "lat","latitude"
   "log","longitude"

By default the plugin uses OpenWeatherMap provider. If you want to use EarthTools you have to set it in ``<property name="provider" value="earthtools"/>``.

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
   
   Download
--------
`Download plugin latest version <https://bintray.com/freedomotic/freedomotic-plugins/download_file?file_path=twilight-5.6.x-3.0_0.device>`_

Source code
-----------
`GitHub repository <https://github.com/freedomotic/freedomotic/tree/master/plugins/devices/twilight>`_
