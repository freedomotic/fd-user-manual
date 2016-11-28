
Push Notifications
==================

**Description**: This plugin can send custom push messages through many providers everytime you want

**Type:** Driver - **Categories:** Network & Communication, Utilities

**Development status:** Beta version

**Tested on:** All platforms

**Developer:** Matteo Mazzoni

Overview
--------

Features
--------

- Global and per-user notification params
- Global notification: send a common notification through a globally configured provider
- Per-user-state notification: notify user using a different provider given his/her state
- Group notification: notify multiple users at once (with per-user-state rule)
- Customizable message text with variable substitution
 
Supported providers
-------------------
This plugin could support almost every provider that allows sending notifications with GET or POST http requests.

Currently the plugin ships with predefined configuration blocks for the following providers:

- Prowl - www.prowlapp.com
- PushOver - www.pushover.net
- Notify My Android - www.notifymyandroid.com
- LiveNotifier - www.livenotifier.net
- Trendoo (SMS Provider) - www.trendoo.it
- Pushsafer - www.pushsafer.com

If you need to use a different provider, please ask me to add proper configuration, or, if you feel brave, have a look at your provider's API and write a configuration block in the plugin manifest file.

Configuration
-------------

First of all, register on the provider and request needed api keys and/or application keys.

Go to plugin manifest file (or open plugin configuration from Freedomotic Frontend), find the proper configuration block and add missing apikey params. In the end, activate the provider changing the  <property name="active" value="TRUE" /> .

Templating
When customizing message string, you can insert variable placeholders that will be substituted with event-related data everytime a notification is sent. Look at the first configuration block for hints.

<property name="param.message" value="Looks like ${event.object.name} power state changed to ${event.object.behavior.powered}" />
 
Usage
Global notification
The easiest way of using Push Notification is creating a Reaction, and linking a Trigger with the predefined Command "Send push notification". Please note, such Command has to be modified in order to use your desired provider and/or customize params.

This usage allows definition of a common way of notifying many events.

Per user notification
Want to provide different notification scenarios for every user? e.g. notify Tom through SMS only when he's not at home.

What to do:

As for global notification, define a reaction, but use the Command "Notify users". e.g. "When a electric device is clicked, notify users"
Add a Person object to the environment, set his name to Tom (or whatever name)
Close Freedomotic, find Tom's object file (under /data/furn/YOUR_ENVIRONMENT/obj/ ), open it with an editor and find the block

.. code:: xml

   <com.freedomotic.model.object.PropertiesBehavior>
       <name>properties</name>
       <description></description>
       <active>true</active>
       <priority>-1</priority> 
       <readOnly>false</readOnly>
       <properties>
            <property name="birthdate" value="01/01/1900"/> 
            <property name="email" value="info@freedomotic.com"/>
       </properties>
    </com.freedomotic.model.object.PropertiesBehavior>

If not present, add a line <property name=mobile" value="" /> after <property name="email" .... /> and set its value with Tom's mobile phone number (international format)
Save and close

Next time you run Freedomotic, Tom's ready to receive SMS notifications!