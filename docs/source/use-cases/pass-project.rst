
PAss Private Assisted House
===========================

The PAss team is headed by dr. Francesco De Angelis, who is working together with INRCA and Regione Marche, on a complete platform that integrates and coordinates home automation, telemedicine solutions and smart objects in the same house.

A "smart house" meta-model is being developed as a result of a multidisciplinary collaboration team of the University of Camerino (architecture and computer science), the Rehabilitation Institute Santo Stefano (http://www.sstefano.it/) and many manufacturers located in Regione Marche, Italy(https://www.google.pt/maps/place/Marche,+Italy). These manufacturers produce hardware, mainly telemedicine devices and also everyday objects are being trasformed into "smart devices" with some form of integration with sensors/actuators.

Freedomotic was chosen as the platform for integration of domestic smart objects (sensors and actuators) in the home environment. These objects can communicate through a home gateway using a JSON payload carried on MQTT.

This architecture was designed for a dual purpose:

#. generating in local, house events to be fed to Freedomotic and create automations according to the rules if-then-else
#. carrying the  data to an internet data center that integrates house-related information with telemedicine data. This data is then treated by ad-hoc algorithms -  which knowing the disability/disease of those who live in the house- can trigger a remote control mechanism and lift alerts to a caregiver . I can be also used to fire in-house automations from outside.

As an example, one of our partners, is developing an app that uses Bayesian networks to control the "normal" patients' behavior. This project aims to develop a mobile UI to be allocated to health care professionals and patients themselves. 

This should simplify as much as possible the daily operations inside the house.

Warning : It is not intended, at the time, to let users configure their house environment and its devices.

Resources
---------

- `Italian thesis <http://www.slideshare.net/freedomotic/tesi-camerino>`_
- `PAss Private Assisted House Project <http://www.projectpass.eu/default.aspx>`_
- `PAss Forum Pa Challenge SlideShare <http://www.slideshare.net/barbaraunicam/p-ass-forum-pa-challenge>`_

Video
-----

.. raw:: html

    <embed>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/Pgzpgh2dlo0" frameborder="0" allowfullscreen></iframe>
    </embed>
