
Twilight - Sunset and sunrise alerts
====================================

**Description**: This plugin sends events related to Sunrise and Sunset time for the configured lat/long

**Type:**  - **Categories:** 

**Development status:** Beta version

**Tested on:** All platforms

**Developer:** Matteo Mazzoni

Overview
--------


Configuration
-------------

Parameters
Parameter	Meaning
lat	latitude
long	longitude

Events are populated with following properties

Property	Meaning	Values
isSunrise	sunset happened a few seconds ago	true or false
isSunset	sunset happened a few seconds ago	true or false
beforeSunset	minutes before the sun sets	int value
afterSunset	minutes after the sun set	int value
beforeSunrise	minutes before the sun rises	int value
afterSunrise	minutes after the sun rose	int value