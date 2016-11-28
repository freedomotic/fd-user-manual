
Download
========

Latest stable release (recommended)
-----------------------------------

This is the currently **RECOMMENDED** versions for most users. You can also try the latest dailybuild if you feel brave.

+--------------------------------------------------------------------------------------------------------------------------------+--------------+-----------+--------------+-------+
| Release                                                                                                                        | Java Version | Size (MB) | Release Date | Notes |
+=====================================+==========================================================================================+==============+===========+==============+=======+
| `Freedomotic Commander RC3 <https://sourceforge.net/projects/freedomotic/files/freedomotic-commander-5.6.0-rc3.zip/download>`_ | JRE 8+       | 45        | 1 Jul 2016   |       |
+--------------------------------------------------------------------------------------------------------------------------------+--------------+-----------+--------------+-------+
| `Freedomotic Commander RC2 <https://sourceforge.net/projects/freedomotic/files/freedomotic-commander-5.6.0-rc2.zip/download>`_ | JRE 8+       | 45        | 16 Nov 2015  |       |
+--------------------------------------------------------------------------------------------------------------------------------+--------------+-----------+--------------+-------+
| `Freedomotic Commander RC1 <https://sourceforge.net/projects/freedomotic/files/freedomotic-commander-5.6.0-rc1.zip/download>`_ | JRE 8+       | 45        | 17 Oct 2015  |       |
+--------------------------------------------------------------------------------------------------------------------------------+--------------+-----------+--------------+-------+
| `Freedomotic Bender 5.5.1 <https://sourceforge.net/projects/freedomotic/files/freedomotic-bender-5.5.1.zip/download>`_         | JRE 6+       | 44        | 11 Mar 2014  |       |
+--------------------------------------------------------------------------------------------------------------------------------+--------------+-----------+--------------+-------+

`Downloads statistics on Sourceforge <http://sourceforge.net/projects/freedomotic/files/stats/timeline>`_

Dailybuilds
-----------

These releases are created daily by our Continuous Integration System on Jetbrains Teamcity. Try one of them if you want to be on the bleeding edge of Freedomotic development.

**These releases are unstable** so don't use them in production environments.

`Download the latest available dailybuild (JRE 8+ required) <http://teamcity.jetbrains.com/guestAuth/repository/download/bt1177/.lastSuccessful/freedomotic-5.6.0-%7Bbuild.number%7D.zip>`_

.. note:: The dailybuilds are created and stored on an external host (teamcity.jetbrains.com). Sometimes it is down due to maintenance, we are sorry for the inconvenience, please be patient.

Docker container (experimental)
-------------------------------

TO BE COMPLETED


For those of you willing to try Freedomotic dailybuild inside a Docker environment, we just created a demo container with some simple usage instructions.
Given you have docker installed on your machine, giving it a try is as simple as running
 
.. code:: 
      
      docker run -p 9111:9111 freedomotic/freedomotic
     

RestApi interface will be available on port 9111 of host machine after a few seconds.
For tech details please go to https://hub.docker.com/r/freedomotic/freedomotic/.

On next days we'll try to test P2P feature in a docker environment with (at least) two Freedomotic instances. 
If you think there may be more interesting usage scenarios for such containers, just share!

Debian packages
---------------


Old releases
------------

Do not use them. These are listed here just for historical reasons. No support will be provided for these versions.
