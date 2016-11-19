
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

.. code-block:: guess

   KEY_SAVE_LOG_TO_FILE = INFO

