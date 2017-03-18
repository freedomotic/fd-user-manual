Raspberry Pi
============

Get Raspbian OS and install it on an SD card
--------------------------------------------
You can follow the Quick Start guide on the official site.

If you already have an SD card with a working Raspbian OS skip this entirely and start from **Install Freedomotic automatically**

 
Install Freedomotic automatically
---------------------------------
After you have a working Raspian OS you can install Freedomotic on it.

Insert your SD card on Raspberry, boot your system and connect using SSH. On Linux write this on command line

.. code-block:: guess

      ssh pi@YOUR_RASPBERRY_IP
       
Default password is **raspberry**.

Open Terminal and copy/paste this command to install and start Freedomotic automatically

.. code-block:: guess

      sudo curl -s http://freedomotic-user-manual.readthedocs.io/scripts/freedomotic-raspberry-install | sh

Some things you would like to know:

* Java 8 is required and it is available on Raspbian OS by default.
* In this example Freedomotic runs in "server mode" without a graphical interface but with an embedded web client.
* Open your browser and point to http://ip-raspberry:8090. As credentials use **admin/admin**.
