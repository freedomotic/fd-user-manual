
MQTT Broker
===========

**Description**: A broker for MQTT protocol based on Moquette library

**Type:** Driver  - **Categories:** Automation Protocols, IoT

**Development status:** Prototype

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------
This plugin adds a MQTT broker to Freedomotic so you can manage this protocol without using an external broker.

It uses an embedded instance of `moquette <https://github.com/andsel/moquette>`_, a Java small MQTT broker implementation.

Configuration
-------------
By default it uses 0.0.0.0 as server ip and 1883 as port number. 

If you want to customize them please edit the previous properties in *mqtt-broker-manifest.xml* file located in the plugin folder.

How to manage a thing
---------------------

* In **Jfrontend** add a thing on the map. Right click on its icon, go to **Control Panel** and set **mqtt-broker** in the protocol field and the mqtt topic in the **address** field. 

* In **Data Source** panel select **MQTT reads a value** in the trigger list.



Multiple behaviors
------------------

Video
-----

.. raw:: html

    <embed>
    <iframe width="420" height="315" src="https://www.youtube.com/embed/sE9sltct_iE" frameborder="0" allowfullscreen></iframe>  </embed>
    </embed>
    
Download
--------
`Download plugin latest version <https://bintray.com/freedomotic/freedomotic-plugins/download_file?file_path=mqtt-broker-5.6.x-3.0.device>`_

Source code
-----------
`GitHub repository <https://github.com/freedomotic/freedomotic/tree/master/plugins/devices/mqtt-broker>`_
