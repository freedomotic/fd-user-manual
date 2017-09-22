Raspberry Pi
============

Get Raspbian OS and install it on an SD card
--------------------------------------------
You can follow the Quick Start guide on the official site.

If you already have an SD card with a working Raspbian OS skip this entirely and start from **Install Freedomotic automatically** section.

 
Install Freedomotic automatically
---------------------------------
After you have a working Raspian OS you can install Freedomotic on it.

Insert your SD card on Raspberry, boot your system and connect using SSH. On Linux write this on command line

.. code-block:: guess

      ssh pi@YOUR_RASPBERRY_IP
       
Default password is **raspberry**.

Open a terminal and copy/paste this command to install and start Freedomotic automatically

.. code-block:: guess

      sudo curl -s https://raw.githubusercontent.com/freedomotic/freedomotic/master/scripts/installation/freedomotic-raspberry-install | sh

Some things you would like to know:

* Java 8 is required and it is available on Raspbian OS by default.
* In this example Freedomotic runs with a graphical interface and an embedded web client. If you want to run it in *server mode* please remove the plugin **frontend-java** under *plugins/devices* folder.
* To try the web client open your browser and point to http://ip-raspberry:8090. As credentials use **admin/admin**.
