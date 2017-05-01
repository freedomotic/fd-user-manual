
Text To Speech
==============

**Description**: A TTS plugin to convert text to sound based on the eSpeak Speech Synthesizer

**Type:** Driver - **Categories:** Speech Recognition & TTS

**Development status:** Beta version

**Tested on:** All platforms

**Developer:** Enrico Nicoletti

Overview
--------

This plugin can be used to speak any text after an event occurs. It is completely programmable using the automations system (if this then say that).

Configuration
-------------

Automations examples
--------------------

Text to speech plugin comes with these predefined **commands** as 

* ``say current time``
* ``say current temperature of the termometer``
* ``say electric device status``
* ``say door/window status``
* ``say readed motion level``

which can be attached to any trigger to creates **automations** like:

* ``if an object is clicked`` -> ``say electric device status``
* ``a door becomes open`` -> ``say door/window status``

... and so on

How to create new custom commands
---------------------------------

* Right click on an object and switch to **Automations tab**
* In command box write ``say current time`` or any other say something command, so you can use it as a template for yours
* Click the edit button. In the next window change the say property according to your needs (remembed you can use token substitution to insert variables like ``@event.object.name``)
* Save as new command

Now your command will be available to be used in automations.

How to install better, natural sounding voices
----------------------------------------------

Default voices have a very metallic sound. To have more natural sounding voices 

- go to the mbrola project website and download the **mbrola** executable for your operative system (under "getting the mbrola binary"). For Linux download from here. For Windows download from here 
- unzip the downloaded archive
- rename the mbrola-SOMETHING executable in "mbrola" (for Linux pc the file is named mbrola-linux-i386)
- put the renamed executable (or mbrola.exe for Windows) into *YOUR_FREEDOMOTIC_FOLDER/plugins/devices/freetts/data/voices*
- put the voice folders (e.g. us1, us2, etc) into *YOUR_FREEDOMOTIC_FOLDER/plugins/devices/freetts/data/voices*
- open the plugin manifest file from **Plugins -> Configure** and set the ``<mbrola-voice>`` key to the voice you want to use (e.g. mbrola_us1, mbrola_us2 etc)
- start Freedomotic

.. note:: Not compatible with openjdk - Oracle jdk required

Video
-----
.. raw:: html

    <embed>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/WvBa30-ibEw" frameborder="0" allowfullscreen></iframe>
    </embed>
  
   