
IpCamera Motion
===============

**Description**: This plugin detecs motion in MPEG streams

**Type:** Driver - **Categories:** Media, Utilities 

**Development status:** Prototype 

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------


Configuration
-------------
* Open the *camera.xml* file and set a name for the camera and the url to access to the stream in your browser (take a look at the examples).

* Double click on the plugin icon to start it. Then right click on the same icon and on **Configure IPcamera plugin** to open the GUI and see all the images from the cameras. 

How to save a captured image
----------------------------
It's possible to save an image when motion is detected by a camera. The default folder is *FREEDOMOTIC_ROOT\plugins\devices\ipcamera-motion\data\captured-images*.

* Open **Manage Automations** (F7 key) and search the trigger "**IpCamera motion detected**". In the command field write "**Capture image from an IpCamera**". Press "Confirm" and the OK. 
