
MaryTTS Text to Speech
======================

**Description**: Text To Speech plugin based on MaryTTS library

**Type:**  - **Categories:** Speech Recognition & TTS

**Development status:** Beta version

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------

This plugin can be used to speak any text when an event occurs. It is completely programmable using the automations system (IF this THEN say THAT).

It's based on MaryTTS project (http://mary.dfki.de/project-summary.html).

Configuration
-------------

Automations examples
--------------------

Text to speech plugin comes with these predefined commands which can be attached to a trigger to create an automation (if you don't know how to do read this chapter of the tutorial):

- say current time
- say current temperature of the termometer
- say electric device status
- say door/window status
-say readed motion level

These commands can be attached to any trigger to create automations like:

- "if an object is clicked" -> "say electric device status"
- "a door becomes open" -> "say door/window status"

...and so on

How to create new custom commands
---------------------------------

Right click on an object and switch to Automations tab. In command box write "say current time" or any other command starting with "say", so you can use it as a template for yours. Click the edit button. In the next window change the say property according to your needs (remembed you can use token substitution to insert variables like @event.object.name). Save as new command. Now your command will be available to be used in automations.

How to install better and natural sounding voices
-------------------------------------------------

By default the plugin uses an English female voice. You can customize it by downloading a new voice, copying the jar file into FREEDOMOTIC_ROOT/plugins/devices/marytts/lib folder and modifying the marytts-manifest.xml file as reported in the following table.

LANGUAGE	VOICE	DOWNLOAD LINK	CONFIG PARAMETERS
English	Female	Already installed	
<property name="voice-jar-file" value="voice-cmu-slt-hsmm-5.1.1.jar"/>

<property name="voice" value="cmu-slt-hsmm"/>
German	Male	http://mary.dfki.de/download/5.1/voice-bits3-hsmm-5.1.zip	
<property name="voice-jar-file" value="voice-bits3-hsmm-5.1.jar"/>

<property name="voice" value="bits3-hsmm"/>
Italian	Female	http://mary.dfki.de/download/5.1/voice-istc-lucia-hsmm-5.1.zip	
<property name="voice-jar-file" value="voice-istc-lucia-hsmm-5.1.jar"/>

<property name="voice" value="istc-lucia-hsmm"/>
