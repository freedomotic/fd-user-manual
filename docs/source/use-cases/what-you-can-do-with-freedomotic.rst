
What you can do with Freedomotic
================================

Security & Video surveillance
-----------------------------

Here a quick solution to create an IP camera for video surveillance by "recycling" an old smartphone / tablet Android you no longer use.

You only need the app https://play.google.com/store/apps/details?id=com.pas.webcam&hl=it

After its installation go to settings and if you decide to leave the default values (no password set) just select the last option **Flow Start**.
At this point you will see the video stream directly on the screen and the URL to open in your browser: something like ``http://ip-smartphone:8080``.

Install the :doc:`IP Camera motion <../plugins/ipcamera-motion>` plugin and open *cameras.xml* file to set the correct ip address.

For example: 

.. code:: 

     <ipcam name="Tablet" url="http://192.168.0.101:8080/video" mode="push"/>

Now the stream captured by the DIY camera is redirected to the plugin so you can detect any motion and execute one or more
commands e.g. sending a notification).

