
What you can do with Freedomotic
================================

Security & Video surveillance
#############################

We propose a quick solution to create an IP camera for video surveillance "recycling" an old smartphone / tablet Android you no longer use.
We only need the app https://play.google.com/store/apps/details?id=com.pas.webcam&hl=it

After installing it we access the settings and if we decide to leave the default (no password) just select the last option **Flow Start**.
At this point we will see the video stream directly on the screen and the URL with which you access from the browser. Something like ``http://ip-smartphone:8080``.

To use our plugin just open *cameras.xml* file (as described :doc:`here <../plugins/ip-camera-motion>`) the following suitably adapted line with the correct ip address. For example:

.. code:: 

     <ipcam name="Tablet" url="http://192.168.0.101:8080/video" mode="push"/>


