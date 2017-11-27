
Jfrontend
=========


Environments
############

Change renderer
***************
This frontend supports different renderers.

.. figure:: images/jfrontend/renderer/change-renderer.png
    :width: 500px
    :align: center
    :height: 350px
    :alt: Change renderer
    :figclass: align-center
    
    Change renderer
    

.. figure:: images/jfrontend/renderer/photo-renderer.png
    :width: 500px
    :align: center
    :height: 350px
    :alt: Photo renderer
    :figclass: align-center
    
    Photo renderer


.. figure:: images/jfrontend/renderer/list-renderer.png
    :width: 500px
    :align: center
    :height: 350px
    :alt: List renderer
    :figclass: align-center
    
    List renderer



.. figure:: images/jfrontend/renderer/image-renderer.png
    :width: 500px
    :align: center
    :height: 350px
    :alt: Image renderer
    :figclass: align-center
    
    Image renderer


.. figure:: images/jfrontend/renderer/plain-renderer.png
    :width: 500px
    :align: center
    :height: 350px
    :alt: Plain renderer
    :figclass: align-center
    
    Plain renderer
    
    

Change background images
************************
Click on **Edit** -> **Environment** -> **Change Background** and select a PNG or a JPG file.


Add a new room
**************
To add a new room, click on **Edit** -> **Room Edit Mode (F5)** and then **Edit** -> **Environment** -> **Add Room**.
A new square polygon will be created on the top left corner of the environment. The blue handles may be dragged to position the room correctly on the map. 

Rename a room
*************
To rename a room, click on **Edit** -> **Environment** -> **Rename Room** and enter the new name into the dialog box. 

Delete a room
*************
To delete a room, select it by clicking on it, then click on **Edit** -> **Environment** -> **Remove Room**.


Edit room shape
***************
To edit the map, simply click on **Edit** -> **Room Edit Mode (F5)**. Now you can drag around the blue handles, to edit the room's shape.
The measures are in centimeters. When you are satisfied with your changes, disable the edit mode in menu **Edit** -> **Room Edit Mode (F5)**.

To add new handles, double click on a pre-existent one. To remove any handle, right-click on it.


Things
######

Move things
***********
By clicking **Edit** -> **Objects Edit Mode (F6)** furniture may be dragged and dropped around the environment. 

Configure things
****************
Right clicking on a thing will display its configuration dialog.


How to add things to the environment map
****************************************
There are two ways to add things to the map:

#. Add it from the toolbar: click on **Edit** -> **Objects Edit Mode** or press **F6**. Now you can see the list of things you can add into your environment. Right click on the thing to be added and choose **Add to environment**. Press F6 again to return to the viewing mode.
#. Clone an already existing thing from the map: select the thing, right click on it, go to **Properties** and press **Create a Copy** button.

A new thing of the same type will be created and placed in the top left corner of the environmnent. To learn how to rename it and move it, read the next paragraph.

How to customize the things icons
*********************************
Thing icons are stored in *FREEDOMOTIC_FOLDER/data/resources*. To edit a thing icon (or create a completely new one) first edit (or create) the PNG image used to represent the thing and put it in the previously mentioned location.

Next, the icon must be associated with the thing. To do so right click on a thing and select the **Representation** tab. Click on **Change Image** and select the custom image that was placed into the *FREEDOMOTIC_FOLDER/data/resources* folder. 

Every thing behavior (on, off, etc.) can have a different icon to represent itself, so you have to repeat the operation for every representation you want to change.
To change the current behavior of a thing, go to the **Control** tab and use the controls to switch it, then you can change its icon for this behavior, as explaned above.

Connect things to real devices
******************************
In Freedomotic things are independent from the hardware used to drive them. For example: a light object is the same in Freedomotic whether it is being controlled by OpenWebNet, Arduino, z-wave, or something else.

First, ensure that the right driver plugin is installed. If not, install it by following the plugin-specific instructions on its marketplace page.

To bind any thing with a specific protocol, you have to right click on the thing to open its configuration dialog. Now go to the **Commands** tab and bind the thing to generic actions like ``turn on`` and ``turn off`` with the specific hardware command to execute it. For example a light ``turn on`` action can be bound with ``turn on OpenWebNet (OWN) light`` command selected from the list on the right.

.. figure:: images/jfrontend/things/thing-configuration.png
    :width: 500px
    :align: center
    :height: 350px
    :alt: Connect a thing to a real device
    :figclass: align-center
    
    Connect a thing to a real device


Localization
############
Freedomotic can detect your PC configuration and set the correct language.

If it's not available or you have chosen the default value **auto**, then the software uses **English**.

.. figure:: images/jfrontend/localization/languages.png
    :width: 500px
    :align: center
    :height: 350px
    :alt: Freedomotic Multilanguage Support
    :figclass: align-center
    
    Multilanguage Support

Automations
###########
In Freedomotic, automations are more powerful than simple, timed turn on/off of objects. They can be created in nearly any natural language (we are working on it) in the form ``if this happens, then do that``.

Event Driven Automations
************************
To create a new automation, right click on the related thing, switch to **Automations Tab** and start to write your command into the input box related to the trigger you desire for your command.

For example:

#. Right click on a light.
#. Select the **Automations** tab.
#. Type ``switch its power`` in the input box corresponding to the trigger ``if XXX is clicked``.
#. Click **OK**.

The light will now turn on and off when it is clicked.

Time Driven Automations
***********************
For timed automations such as ``Do something every minute``, a **Clock** object is needed. If one is not already on the map, add it by pressing F6 and double clicking on the **Clock** thing on the list on the left side of the screen.

Right click on the new object, select the automations tab and create the automation in the same manner as the Event Driven Automations (explained above). For example: ``Switch power for all lights every 5 seconds``.

Right click on the clock object and select the **Automations** tab, or use the automations editor, which lists all available triggers.
Find the trigger ``every 5 seconds`` and link it to the command ``switch power for all lights``.



Plugins
#######

Download new features from the marketplace
******************************************
In the **Plugins** menu click **Install from marketplace**. After the list is updated (it can take up to a minute) the list of plugins in the markeplace that are available for your current Freedomotic version will be displayed.
To install one, double click on it and follow the instructions.

.. figure:: images/jfrontend/plugins/install-from-marketplace.png
    :width: 500px
    :align: center
    :height: 350px
    :alt: Install plugins from marketplace
    :figclass: align-center
    
    Install plugins from the marketplace


Start and stop plugins
**********************
Loaded plugins are visible in the list on the left of the environment map. Running plugins are represented by a coloured icon.
To start a plugin (or to stop an already running plugin), double click on its name. When a plugin is running, the feature it provides is available to the system.
For example the OpenWebNet plugin enables communication with BTicino OpenWebNet (OWN) devices. This means the plugin doesn't provide automations to drive OWN devices itself but only "translates" the Freedomotic user commands as ``turn on kitcken light`` into hardware-level specific commands. This allows you to forget about hardware and internal communication details. Simply say ``turn on kitchen light``, and Freedomotic takes care of the rest.

.. figure:: images/jfrontend/plugins/plugin-list.png
    :width: 500px
    :align: center
    :height: 350px
    :alt: Plugins list
    :figclass: align-center

    Plugins list    

How to configure a plugin
*************************
Some plugins offer a configuration dialog to interact with its features. To view it, right click on the plugin name. 
For an example, try this on the **"Sensors Simulator"** plugin, which is a development tool to simulate a temperature and luminosity sensor.
You can make this fake sensor notify a temperature change to Freedomotic, by moving the **temperature** slider. 

.. figure:: images/jfrontend/plugins/sensors-simulator.png
    :width: 500px
    :align: center
    :height: 350px
    :alt: Sensors Simulator Plugin
    :figclass: align-center

    Simulator Plugin

.. note::  Not all plugins have a configuration dialog, so if you right click and nothing shows, it is because the plugin have no configuration options.


Settings
########

Help
####

