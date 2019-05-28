
Arduino WeatherShield
=====================

**Description**: With this plugin Freedomotic can communicate with Arduino WeatherShield by Ethermania.com.

**Type:**  - **Categories:** 

**Development status:** 

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------
The WeatherShield, created by [Ethermania.com](http://www.ethermania.com/), is a unit that lets Arduino able to read Pressure, Temperature and Relative Humidity. The shield is equipped with three sensors and a PIC12F683 microcontroller programmed with a specific firmware that interfaces with Arduino through a two line bidirectional synchronous serial connection. The microcontroller is responsible for sampling and averaging the last 8 humidity, pressure and temperature values, providing it to the Arduino in an ASCII readable format expressed in Celsius, hPa and relative % units. More details can be found [here](http://www.ethermania.com/shop/index.php?main_page=product_info&cPath=91_104&products_id=612&language=en).

.. figure:: images/arduino-weathershield/arduino-weathershield.jpg
    :width: 600px
    :align: center
    :height: 400px
    :alt: Arduino WeatherShield
    :figclass: align-center

    Arduino WeatherShield 

Board protocol
--------------
The proposed solution uses an ethernet shield to connect Arduino board to your lan. On Arduino you must upload the included sketch to interact with the WeatherShield to retrieve sensors values and shows them as a string with ":" char as delimiter. Also you must add to your Arduino IDE the WeatherShield lib (included into PLUGIN_ROOT/resources/WeatherShield/WeatherShieldLibrary).

The default address is 192.168.0.150 on port 80. If you desire to change it you must edit the sketch, recompile and upload to Arduino board. To verify if it works open your browser and digit the board address "http://192.168.0.150". You would see a string reporting the sensors values.

How to read values from an object
---------------------------------
With this board you can read the temperature behavior of any thermometer device in your environment.

For this example we use a thermometer object:

Right click on the thermometer object in the environment to show its configuration panel
Change the property "protocol" to "ArduinoWeatherShield"
Change the property "address" to a string composed of HTTP_BOARD_URL:HTTP_PORT. For example "192.168.0.150:80:T" identifies the board listening on 192.168.0.150:80 for temperature values (use "P" for pressure and "H" for humidity). 
Under "temperature" (in Data Source Configuration) select the trigger called "Arduino WeatherShield reads temperature change"
 The plugin is also able to read any humidity and pressure change.

From Freedomotic 5.6 version it uses autodiscovering feature so 3 new things (thermometer, barometer and hygrometer) are added and configured automatically.

Source code
-----------
Hosted [here](https://github.com/freedomotic/freedomotic/tree/master/plugins/devices/arduino-weathershield)

