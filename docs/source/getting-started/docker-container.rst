Docker container
================

Given you have Docker already installed on your machine you can start the container with the following instruction
 
.. code:: 
      
      docker run -d --name=freedomotic -p 9111:9111 -p 8090:8090 ghcr.io/freedomotic/freedomotic-5.6.0:dailybuild
     

After a few seconds RestAPI interface will be available on port 9111 and the web client on port 8090 of the host machine. 
So point your browser to http://ip-docker-server:9111 or to http://ip-docker-server:8090.


.. note:: The latest version is mapped to **[dailybuild]** tag. If you want to try another version please specify the correct tag as in the following table. 

.. csv-table:: Docker images
   :header: "Tag", "Architecture", "Hw platforms", "Notes"
   :widths: 10, 30, 40, 20
   
   "latest","x86_64","Windows, Linux, Mac OS X","points to the last dailybuild"
   "dailybuild","x86_64","Windows, Linux, Mac OS X",""
   "armhf","ARMv7","Raspberry Pi v1-2",""
   "arm64","ARMv8","Raspberry Pi v3, Odroid C2",""


Container health check
----------------------

Our images use Docker helth check feature to ensure the application is running correctly.
Every 5 minutes Docker verifies if the web client is up and stops the container with a code error if it doesn't receive a response
by 3 seconds. The first check starts after 10 seconds.



Data persistence
----------------

Docker, by default, doesn’t come with persistent storage so when the container is removed all data is lost.
To fix the problem you need to use Docker volumes.

Our images expose two volumes: **["/srv/freedomotic/data"]** and **["/srv/freedomotic/plugins"]**. 

The first contains all data
(commands, triggers, reactions, environments and things) and correspond to the *"data"* folder in the package release.
The second contains all the plugins (executables and configuration files) and corrispond to the same named folder in the package
release

Bind mount
**********

The most simple solution is to mount a folder on the host machine and map it to one of the previous volume.

For example if your local Linux folder is *"/home/freedomotic-data"* you have to copy all the files from *"data"* folder included in the 
package release and start the container in this way

.. code:: 
      
      docker run -d --name=freedomotic -p 9111:9111 -p 8090:8090 -v /home/freedomotic-data:/srv/freedomotic/data  freedomotic/freedomotic

So if you remove the container all data is saved on the host.

Data volumes
************

This solution is a little more complicated but very useful if you want to share data with other containers inside a cluster. 

PD: the volume isn't cancelled if you remove the container.

Here a step by step guide:


* Create a new volume named **"FreedomoticVolume"**

.. code:: 
      
      docker volume create --name FreedomoticVolume
      
* Create a temporary container to copy the data. It's based on a minimal image (busybox) and mounts the volume under the path *"/data"*

.. code:: 
      
      docker create -v FreedomoticVolume:/data --name temp busybox
     
* Download a Freedomotic package or reuse an existing installation. In every case you need to move to the *"data"* folder and copy its content inside the Docker volume. In order to do this we use **"temp"** container previously created

.. code:: 
      
      docker cp . temp:/data
      
* Remove **"temp"** container

.. code:: 
      
      docker rm temp
      
* Start Freedomotic container using **"FreedomoticVolume"**


.. code::

      docker run -d --name freedomotic -v FreedomoticVolume:/srv/freedomotic/data -p 9111:9111 -p 8090:8090 freedomotic/freedomotic

In case of problems you can take a look at the logs with

.. code::
  
      docker logs freedomotic

Backup
******

TODO


Docker Hub
----------

All the official images are hosted on `Docker Hub <https://hub.docker.com/r/freedomotic/freedomotic/>`_.

On next days we'll try to test P2P feature in a Docker environment with (at least) two Freedomotic instances. 
If you think there may be more interesting usage scenarios for such containers, just share!
