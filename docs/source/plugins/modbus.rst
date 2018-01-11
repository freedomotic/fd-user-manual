
Modbus
======

**Description**: 

**Type:**  - **Categories:** 

**Development status:** 

**Tested on:** All platforms

**Developer:** Gabriel Pulido de Torres

Overview
--------
This plugin allows Freedomotic to be configured as a Master device in the Modbus network to read values from the slaves of the system.

The read values are then published as events in the system.

NOTE: from 5.6 version TCP and RTU over TCP are supported.

Configuration
-------------
The sensor usual parameters should be configured. See the Sensor page. Also the following parameters must be defined in the xml manifest file.



.. csv-table:: Generic properties
   :header: "Parameter","Required","Values","Effect","Note"
   :widths: 20, 20, 20, 20, 20

   "modbus-protocol","yes","'RTU' or 'TCP'","Configuration for RTU or TCP"
   "port","yes","'COM1' or '/dev/ttyUSB0'","Name of the Serial port used","Only needed if modbus-protocol is RTU"
   "baudrate","yes",,"Serial Port Parameter","Only needed if modbus-protocol is RTU"
   "data-bits","yes",,"Serial Port Parameter","Only needed if modbus-protocol is RTU"
   "parity","yes","0|1|2","Serial Port Parameter","Only needed if modbus-protocol is RTU"
   "stop-bits","yes",,"Serial Port Parameter","Only needed if modbus-protocol is RTU"
   "host","yes","IP address","TCP host address","Only needed if modbus-protocol is TCP"
   "tcp-port","yes","Port","TCP host port","Only needed if modbus-protocol is TCP"
   "encapsulated","yes",,"RTU over TCP flag","Only needed if modbus-protocol is TCP and you want to enable RTU over TCP"
   "timeout","yes",,"Time in milliseconds","Modbus Parameter"
   "retries","yes",,"Number of retries to obtain a value","Modbus Parameter"
   "NumRegisters","yes","0|..|n","Number of registers that are going to be configured","This value should match the total of tuples defined"


For every register that is going to be read from the network a tuple should be configured with the correct parameters to locate and transform from the modbus system to Freedomotic system as one Event. For every tuple, the sensor sends an event on the Freedomotic system.

Tuples properties
Parameter	Required	Values	Effect	Note
Name	yes	String with the name of this value in the system	 	Must be unique in the sensor
SlaveId	yes	0|..|n	Number of the slave from which the value is read	 
RegisterRange	yes	See table of Register Ranges allowed	 	 
DataType	yes	See table of Data Type allowed	 	 
Bit	no	0|..|n	Sets the bit to be read from the Binary register	It is only used when the DataType is set to Binary
Offset	yes	0|..|n	Address of the register to be read in the slave	 
NumberOfRegisters	no	0|..|n	Number of consecutive registers to be read	Not used at this moment
Multiplier	no	double value	Used with the Additive parameter to transform the value from the modbus scale system to the Freedomotic scale system	Mx+A where M= Multiplier x= value readed A= Additive
Additive	no	double value	Used with the Additive parameter to transform the value from the modbus scale system to the Freedomotic scale system	Mx+A where M= Multiplier x= value readed A= Additive
EventName	yes	String	Name of the parameter in the event that is going to be sent with the value	This value configures a GenericEvent with a parameter with name="EventName" value="Mx+A"


Register Ranges:
Name	Note
COIL_STATUS	 
INPUT_STATUS	 
HOLDING_REGISTER	 
INPUT_REGISTER

Data Types
Name	Note
BINARY	 
TWO_BYTE_INT_UNSIGNED	 
TWO_BYTE_INT_SIGNED	 
FOUR_BYTE_INT_UNSIGNED	 
FOUR_BYTE_INT_SIGNED	 
FOUR_BYTE_INT_UNSIGNED_SWAPPED	 
FOUR_BYTE_INT_SIGNED_SWAPPED	 
FOUR_BYTE_FLOAT	 
FOUR_BYTE_FLOAT_SWAPPED	 
EIGHT_BYTE_INT_UNSIGNED	 
EIGHT_BYTE_INT_SIGNED	 
EIGHT_BYTE_INT_UNSIGNED_SWAPPED	 
EIGHT_BYTE_INT_SIGNED_SWAPPED	 
EIGHT_BYTE_FLOAT	 
EIGHT_BYTE_FLOAT_SWAPPED	 
TWO_BYTE_BCD	 
FOUR_BYTE_BCD

An XML example
--------------

This xml file configures 2 registers.

The first register reads a temperature value from the slave and, as the Modbus in this example stores the value multiplied by 10, the sensor transforms that value multiplying it by 0.1

The second register reads the bit value from position 6 from the register.

.. code::

   <config>
      <properties>
          <property name="description" value="Plugin for Modbus protocol"/>
          <property name="category" value="protocol"/>
          <property name="short-name" value="modbus"/>
          <property name="polling-time" value="1000"/>
          <property name="NumRegisters" value="2"/>
          <property name="port" value="/dev/ttyUSB10"/>
          <property name="baudrate" value="19200"/>
          <property name="data-bits" value="8"/>
          <property name="parity" value="2"/>
          <property name="stop-bits" value="1"/>
          <property name="timeout" value="10000"/>
          <property name="retries" value="2"/>
      </properties>
      <tuples>
          <tuple>
            <property name="Name" value="TemperatureZone1"/>
            <property name="SlaveId" value="1"/>
            <property name="RegisterRange" value="HOLDING_REGISTER"/>
            <property name="DataType" value="TWO_BYTE_INT_UNSIGNED"/>
            <property name="Offset" value="266"/>
            <property name="NumberOfRegisters" value="1"/>
            <property name="Multiplier" value="0.1d"/>
            <property name="Additive" value="0.0d"/>
            <property name="EventName" value="TemperatureZone1"/>
          </tuple>
          <tuple>
            <property name="Name" value="BitTest"/>
            <property name="SlaveId" value="1"/>
            <property name="RegisterRange" value="HOLDING_REGISTER"/>
            <property name="DataType" value="BINARY"/>
            <property name="Bit" value="6"/>
            <property name="Multiplier" value="1"/>
            <property name="Additive" value="0"/>
            <property name="Offset" value="256"/>
            <property name="NumberOfRegisters" value="1"/>
            <property name="EventName" value="BitTest"/>
          </tuple> 
      </tuples>
  </config>
  
  