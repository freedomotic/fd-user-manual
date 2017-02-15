
openPicus Grove System
======================

**Description**: This plugin reads data from a Grove Nest sensors board

**Type:** Driver - **Categories:** Automation Protocols

**Development status:** Prototype

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------
The plugin acts as a simple udp server listening for packets from Grove Nest boards. When it receives a packet, it extracts the data (Grove Nest ip address, sensor connector, sensor value). Then it notifies the event on the Freedomotic messages channel and updated the specific object.

Configuration
-------------

The plugin acts as a simple udp server listening for packets from Grove Nest boards. When it receives a packet, it extracts the data (Grove Nest ip address, sensor connector, sensor value). Then it notifies the event on the Freedomotic messages channel and updated the specific object.

The firmware code is included in the taskFlyport.c. Let's analyze it step by step.

First of all the libraries required for Grove Nest and analog temperature sensor are included.

.. code::

  #include "taskFlyport.h"
  #include "grovelib.h"
  #include "analog_temp.h"

Now let's create an integer variable for udp socket reference, a char array for sending messages and udp server ip address and port number. The last parameters are used by Freedomotic plugin. If you change these you must change also the flyport variables.

.. code::

  int clientUDPsocket;
  char send[120];
  void FlyportTask()
    {	
      BYTE Socket=0;    //UDP Socket
      char *UDPPort="7331"; //UDP port
      char *UDPAddress="192.168.1.100";

The next step is defining variables for grove nest and used sensors and attaching them to the board. The float variables are used to store the new and the old sensors values.

.. code:: 
   //GROVE board
   void *board = new (GroveNest);
   // GROVE devices
   // Light sensor
   void *light_sensor = new (An_i);
   // Analog Temperature Sensor
   void *temp_sensor = new(An_Temp);
   // Sensor attached to board
   attachToBoard(board, temp_sensor, AN1);
   attachToBoard(board, light_sensor, AN3);
   float lightVal = 0.0;
   float lightValStored = 0.0;
   float tempVal = 0.0;
   float tempValStored = 0.0;
   
The application core is included into the infinite loop. It detects the new sensor value, compares it with the stored one and if there is a change sends a new udp packet to the Freedomotic server whit a prefixed message format: connector:sensorType:value. The char ":" is the string delimiter. The allowed sensor types are (in this example) temperature and luminosity. You can't change them without changing the Freedomotic plugin code because it makes a string parsing to extract the data. After the socket is closed.

.. code::

 while(1)
  {
    vTaskDelay(500);
    //Socket=UDPClientOpen(UDPAddress,UDPPort);
    // Get the new temperature value
    tempVal = get(temp_sensor); 
    if(tempVal!=tempValStored) {
     	tempValStored=tempVal;
        sprintf(send,"AN1:temperature:%3.1f", (double)tempVal);
    	Socket=UDPClientOpen(UDPAddress,UDPPort);
        UDPWrite(Socket,send,strlen(send));  //Send the data trough the UDP
        UDPClientClose(Socket);
       }
      // Get the new luminosity value using the get() function
      lightVal = get(light_sensor);
      if(lightVal!=lightValStored) {
           lightValStored=lightVal;
           sprintf(send,"AN3:luminosity:%3.0f", (double)lightVal);
           Socket=UDPClientOpen(UDPAddress,UDPPort);
           UDPWrite(Socket,send,strlen(send));  //Send the data trough the UDP
           UDPClientClose(Socket);
           }
       }
   }


No packets are sent if there is no sensor data change. This reduces the network traffic.

The list of materials
---------------------

* A Flyport_WiFi
* A Grove_NEST
* A GROVE_-_Light_Sensor
* A GROVE_-_Temperature_Sensor_Analog

The build process
-----------------

**Software**

* Download the Grove System project package and extract it into a new folder.
* Open the openPicus IDE, and from the environment open the project folder.
* Click the “Compile” button, and when the operation is completed click “Download” so that the new firmware is downloaded in the Flyport's microcontroller.

**Hardware**
Let's connect the analog sensors to the Grove Nest: temperature sensor to AN1 and light sensor to AN3.

Then let's connect the flyport wifi module and the power supply.

Start Freedomotic by double click on its icon or by command line with java -jar freedomotic.jar.
The pc running Freedomotic must have 192.168.1.100 as ip address.
In "Plugins" menu choose "Install from marketplace". After the list is updated (it can take up to a minute) you will see all available plugin categories for your current Freedomotic version. Select Automation Protocols, then Openpicus Grove System icon and click on Install button following the video instructions.

Video
-----
.. raw:: html
  
    <embed>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/KcWl3anjatY" frameborder="0" allowfullscreen></iframe>
    </embed>