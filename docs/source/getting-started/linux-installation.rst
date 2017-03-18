Linux installation
==================

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