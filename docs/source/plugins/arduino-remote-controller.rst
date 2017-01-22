
Arduino Remote Controller
=========================

**Description**: This plugin uses an Arduino board to receive IR signals from a remote controller and execute Freedomotic commands

**Type:**  - **Categories:** Arduino, Automation Protocols, Internet of Things

**Development status:** Prototype

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------

This plugin uses an Arduino board with an ethernet shield to receive IR commands from a remote controller. 
Then it tells Freedomotic which button has been pressed and a specific command is executed (e.g. if you press the button 1 the kitchen light switches on/off).

The plugin consists of two parts a sketch to upload on your Arduino board and the java code. For this test we have used a Leadtek remote for the WinFast TV board. Most of the common remote controllers work well.


Configuration
-------------

First of all you must detect your remote codes using `this library <https://github.com/shirriff/Arduino-IRremote>`_.
You can find a good tutorial `here <http://www.righto.com/2009/08/multi-protocol-infrared-remote-library.html>`_.

Then you must substitute the hex code into the following sketch (included into the plugin package).

.. code:: 

 // Freedomotic Remote Controller Plugin
 // by Mauro Cicolella
 // www.freedomotic.com

 #include <IRremote.h>
 #include <String.h>
 #include <SPI.h>
 #include <Ethernet.h>
 #include <EthernetUdp.h>

 int pinIRreceiver = 11;
 IRrecv IRreceiver(pinIRreceiver);
 decode_results receivedSignal;

 byte mac[] = { 0xDE, 0xAD, 0xBE, 0xEF, 0xFE, 0xED }; // mac address
 byte ip[] = { 192, 168, 0, 2}; // ip arduino
 byte subnet[] = { 255, 255, 255, 0 }; //subnet mask
 byte gateway[] = { 192, 168, 0, 1}; // ip gateway
 EthernetServer server(80); // server web listening on port 80

 /* UDP configuration */
 unsigned int UDPport = 7878;
 EthernetUDP Udp;
 IPAddress ipServerUDP(192, 168, 0, 20);
 unsigned int ServerUDPport = 8000;

 void setup()
 {
   Serial.begin(9600); // serial monitor
   IRreceiver.enableIRIn();
   Ethernet.begin(mac, ip, gateway, subnet);
   Udp.begin(UDPport);
 }

 void loop()
 {
   if (IRreceiver.decode(&receivedSignal)) // received IR signal
   {
     IRreceiver.resume(); // ready to receive the next signal

     switch (receivedSignal.value) {
                                // button 1
                                case 0xC03FA05F:
                                Serial.println("Pressed 1 button");
                                sendUDPpacket('1');
                                break;

                                // button 2
                                case 0xC03F609F:
                                Serial.println("Pressed button 2");
                                sendUDPpacket('2');
                                break;

                                // button 3
                                case 0xC03FE01F:
                                Serial.println("Pressed button 3");
                                sendUDPpacket('3');
                                break;

                                // button 4
                                case 0xC03F906F:
                                Serial.println("Pressed button 4");
                                sendUDPpacket('4');
                                break;

                                // button 5
                                case 0xC03F50AF:
                                Serial.println("Pressed button 5");
                                sendUDPpacket('5');
                                break;
                                }
    }
 }

 void sendUDPpacket(char button)
 {
    Udp.beginPacket(ipServerUDP, ServerUDPport);
    Udp.write("AN1:");
    Udp.write(button);
    Udp.endPacket();
 }
 
To avoid polling Arduino sends an udp packet to the udp server embedded into the plugin. 
The packet has the format **AN1:X** where X represents the pressed button. For example **AN1:1**.
 
The plugin starts an embedded udp server listening by default on address **192.168.0.20** and port **8000**. These values are specified into the manifest file *arduino-remote-controller-manifest.xml*.
If you change them you must consequently change the sketch.

When a new udp packet arrives, the plugin extracts the encapsulated data and notifies Freedomotic an event with the pressed button. 

In the plugin data folder there are some user level triggers called  ``When button X is pressed on remote`` (where X represents the pressed button) filtering the events and their button.pressed property.

Now we can create automations from jfrontend in the form of ``when button X is pressed on remote THEN "ADD HERE ANY FREEDOMOTIC COMMAND"``.

We can make Freedomotic tweet it, turn off all lights, send a mail, speech some text, whatever...

Video
-----

.. raw:: html

    <embed>
    <iframe width="420" height="315" src="https://www.youtube.com/embed/W_j8nUn7Puw" frameborder="0" allowfullscreen></iframe>  </embed>
