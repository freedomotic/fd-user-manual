Persistence
===========

**Description**: Save events and commands on a db Cassandra

**Type:** Driver - **Categories:** Utilities

**Development status:** Proof of Concept

**Tested on:** All platforms

**Developer:** P3trur0

Overview
--------
This plugin allows to persist on Cassandra server both ``commands`` and ``events`` occurred on Freedomotic instances.  
Using this plugin, for each automation available on the platform, the user can run a **Persist data on Cassandra** command that will perform the operation to save data on the database.

Once started, this plugin tries to connect to the Cassandra server defined in its configuration properties (see below).
All the data are saved in a table named ``freedomotic_data``.
It is not required to create it manually since this plugin, once started, automatically detects the existence of ``freedomotic_data`` table creating it if does not exist.

This table contains the following information:

- ``id``, it is the identifier of each persisted row
- ``datatype``, it is either "command" or "event"
- ``data``, it is a binary serialization of persisted event/command
- ``avro_schema``, it is the Avro schema used for serialize/deserialize the persisted data
- ``persistence_timestamp``, it is the persistence timestamp
- ``freedomoticInstance``, it is the identifier of the currently used Freedomotic instance

These data could be later used for any kind of data analysis you would like to perform on Freedomotic usage.
Basically it is required to deserialize the binary serialization data using the Avro schema provided to analyze the original data values properly.

Configuration
-------------

Within the plugin manifest, are defined all the properties available to configure the communication of the plugin with Cassandra instance.
Moreover, you can also specify both the replication factor and strategy of the server instance.

Here follows an example of manifest.

 .. code:: xml

  <config>
	 <properties>
		  <property name="description"
		    value="Cassandra database for storing Freedomotic events and commands" />
		  <property name="name" value="persistence" />
		  <property name="category" value="protocol" />
		  <property name="short-name" value="persistence" />
		  <property name="protocol.name" value="persistence" />
		  <property name="startup-time" value="on load" />
		  <!-- Cassandra configuration -->
		
		  <property name="cassandra.host" value='127.0.0.1'/>
		  <property name="cassandra.port" value='7000'/>
		  <property name="cassandra.keyspace" value='freedomotic'/>
		  <property name="cassandra.replicationFactor" value='1'/>
		  <property name="cassandra.strategy" value='SimpleStrategy'/>
		  <property name="cassandra.user" value='user'/>
		  <property name="cassandra.password" value='password'/>
		
		  <!--  end of cassandra configuration -->
	 </properties>
  </config>


The properties for the Cassandra instance configuration are:

* **cassandra.host**, it represents the Cassandra IP address
* **cassandra.port**, it represents the Cassandra Port
* **cassandra.keyspace**, it is the name of Cassandra keyspace used by freedomotic
* **cassandra.replicationFactor**, it is the replication factor of the data
* **cassandra.strategy**, it is the Cassandra replication strategy
* **cassandra.user**, Cassandra username
* **cassandra.password**, Cassandra password

Requirements
------------

**Persistence** has been tested using Cassandra server (ver. 3.9).
