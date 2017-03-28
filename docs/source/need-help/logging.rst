
Logging
=======

If enabled Freedomotic logs all messages in a file called *freedomotic.log* located in *FREEDOMOTIC_ROOT/log* folder.

It is configured to roll if the size is more than 500Kb.

How to enable logging
#####################
Change the property KEY_SAVE_LOG_TO_FILE in *FREEDOMOTIC_ROOT/config/config.xml* by choosing one of the following values:

* **OFF**: no logging
* **ALL**: all levels
* **LOG LEVEL (INFO | DEBUG | WARN | ERROR)**: specify a log level 

For example

.. code-block:: guess

   KEY_SAVE_LOG_TO_FILE = ALL 
   
or

.. code-block:: guess

   KEY_SAVE_LOG_TO_FILE = INFO

Here a log example

.. code-block:: guess

   date LEVEL [thread] (Class:row) Message
   
   2017-03-27 17:34:10,695 INFO  [main] (BusBroker.java:60) Creating new messaging broker
   2017-03-27 17:34:10,960 INFO  [main] (BusBroker.java:63) Configuring messaging broker
   2017-03-27 17:34:11,314 INFO  [main] (BusBroker.java:66) Starting messaging broker
   2017-03-27 17:34:12,211 INFO  [main] (BusConnection.java:96) Creating connection factory

.. note:: **INFO** is the best choice in many cases  