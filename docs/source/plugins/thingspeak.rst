
ThingSpeak
==========

**Description**: A plugin to publish data on ThingSpeak.com platform

**Type:** Driver  - **Categories:** Utilities

**Development status:** Beta version

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------
This plugin allows to publish data on `ThingSpeak.com <http://thingspeak.com>`_ platform so you can persist things data to create charts and make custom analysis. 


Configuration
-------------

Open the file thingspeak-manifest.xml and set your ThingSpeak API key in ``<property name="api-key" value="api-key-to-set"/>``.

For each thing you want to persist add a ``<tuple></tuple>`` block as the following

.. code:: 

    <tuple>
            <property name="thing-name" value="Thermometer"/>
            <property name="thing-behavior" value="temperature"/>
            <property name="thingspeak-channel" value="XXXXXX"/>
            <property name="thingspeak-field" value="1"/>
    </tuple>

.. csv-table:: Configuration parameters
   :header: "Parameter", "Description", "Values"
   :widths: 30, 30, 20
   
   "thing-name","Freedomotic thing name","e.g. Kitchen Thermometer"
   "thing-behavior","the thing behavior to persist","as in the 'Things behaviors' table"
   "thingspeak-channel","ThingSpeak channel","the channel ID"
   "thingspeak-field","ThingSpeak channel field","1-8"
   
.. csv-table:: Things behaviors
   :header: "Thing class", "Behavior"
   :widths: 30, 30
   
   "Barometer", "pressure"
   "Hygrometer","humidity"
   "Light sensor","luminosity"
   "Thermometer","temperature"
   "Thermostat","temperature"
   
.. note:: Of course you can specify any valid behavior of your things. Please check it is correct and compatible with ThingSpeak field values.     



