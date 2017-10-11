Docker container (experimental)
===============================

For those of you willing to try Freedomotic dailybuild inside a Docker environment, we just created a demo container with some simple usage instructions.

Given you have Docker already installed on your machine you can start the container with the following instruction
 
.. code:: 
      
      docker run -d --name=freedomotic -p 9111:9111 -p 8090:8090 freedomotic/freedomotic
     

After a few seconds RESTapi interface will be available on port 9111 and the web client on port 8090 of the host machine. 
For tech details please go to https://hub.docker.com/r/freedomotic/freedomotic/.

.. note:: The latest version is mapped to [dailybuild] tag. If you want to try another version please specify the correct tag as in the following table. 

.. csv-table:: Docker images
   :header: "Tag", "Architecture", "Hw platforms", "Notes"
   :widths: 10, 30, 40, 20
   
   "latest","x86_64","","points to the last dailybuild"
   "dailybuild","x86_64","","unstable"
   "alpine","x86_64","","small and secure"
   "armhf","ARMv7","Raspberry Pi v1-2",""
   "arm64","ARMv8","Raspberry Pi v3, Odroid C2",""


On next days we'll try to test P2P feature in a Docker environment with (at least) two Freedomotic instances. 
If you think there may be more interesting usage scenarios for such containers, just share!
