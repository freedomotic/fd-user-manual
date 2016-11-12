
Arduino Serial Communication
============================

**Description**: A basic example to communicate with an Arduino board via serial connection

**Type:** Driver  - **Categories:** Arduino, Automation Protocols, IoT

**Development status:** Prototype

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------
This example shows how to control an Arduino board connected via usb interface in order to switch on/off a led. 
The code is very simple but it's a base from which to create more complex plugin using serial protocol. 

Configuration
-------------
To configure the plugin open *arduinousb-manifest.xml* in its folder and change the following properties. 
By default you need to change only the port name and set the one in use.

* **serial.port**: port name e.g. /dev/ttyACM0 for Linux or COMx for Windows
* **serial.baudrate**: baudrate of Arduino serial port (the same used in the sketch)
* **serial.databits**: databits of Arduino serial port
* **serial.parity**: parity bit of Arduino serial port
* **serial.stopbits**: stop bit of Arduino serial port
* **chunk.terminator**: read serial string terminator (by default "&#xA;" as "\n")
* **chunk.size**: size of chunk to read from serial
* **delimiter**: fields delimiter in read string

Arduino sketch
--------------

The following sketch must be uploaded to your arduino board. It's very simple: when it receives a char 'a' from serial connection it switch on the led connected to pin 13. Viceversa with 'b' char the led is switched off. Every command writes a string on serial.

.. code-block:: guess

   void setup() {
      Serial.begin(9600);
      //Set all the pins we need to output pins
      pinMode(13, OUTPUT);
    }

    void loop (){
      if (Serial.available()) {

      //read serial as a character
      char ser = Serial.read();

      //NOTE because the serial is read as "char" and not "int", the read value 
      //must be compared to character numbers
      //hence the quotes around the numbers in the case statement
      switch (ser) {
        case 'a':
          pinON(13);
          Serial.println("13;on");
          break;
          case 'b':
          pinOFF(13);
          Serial.println("13;off");
          break;
        }
       }
      }
      
      void pinON(int pin){
        digitalWrite(pin, HIGH);
      }

      void pinOFF(int pin){
        digitalWrite(pin, LOW);
      }

 
