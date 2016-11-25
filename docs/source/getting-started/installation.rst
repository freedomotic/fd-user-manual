
Installation
============

Windows
#######

* Download Freedomotic from :doc:`here <download>`
* Unzip the downloaded file
* Double click on **freedomotic.exe** located into FREEDOMOTIC\_ROOT folder (the extracted folder)

 
Linux
#####

* Download Freedomotic from :doc:`here <download>`
* Unzip the downloaded file
* Double click on **freedomotic.sh** or open the terminal and execute

.. code::
      
      ./freedomotic.sh

 
Linux Debian package
####################

* Download Freedomotic Debian package from :doc:`here <download>`
* From command line digit 

.. code::

      sudo dpkg -i freedomotic_5.5.1.deb 

or use your preferred packages manager. The installation could require some missing dependencies. In this case digit 

.. code::

      sudo apt-get install -f

You can now call Freedomotic with SUDO (no problem, it automatically runs as "**freedomotic**" user) but your Linux user won't be able to access config files unless it belongs to group "**freedomotic**",
so the best choice is to issue a 

.. code::

      sudo adduser <your-username> freedomotic
      
exit and re-login. You no longer need to SUDO when calling Freedomotic.

* Start Freedomotic from command line with

.. code::

      ./freedomotic

or click on the **Application Menu** item.

 
Mac OsX
#######

* Download Freedomotic from :doc:`here <download>`
* Unzip the downloaded file
* Open the terminal (**/Applications/Utilities/** folder), go to Freedomotic root folder (the extracted folder) and type the following command

.. code::

   java -jar "freedomotic.jar"

Raspberry Pi
############

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
