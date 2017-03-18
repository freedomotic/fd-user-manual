Basic configuration
===================

All the configuration parameters are included in the file *FREEDOMOTIC_ROOT/config/config.xml*.

Default values are put in squared brackets.


Basic
~~~~~

These properties are used to start the framework so **don't change the default values** if not strictly needed.

* **KEY_BROKER_URL [vm\://localhost?persistent\=false]**: ActiveMQ broker url
* **KEY_MESSAGES_TTL [5000]**: messages time to live
* **KEY_DISCARD_INVALID_DESTINATIONS [true]**:
* **INSTANCE_ID [random uuid]**: uuid of Freedomotic instance


Internationalization
~~~~~~~~~~~~~~~~~~~~

* **KEY_ENABLE_I18N [auto]**: enable/disable multilanguage support (for more details :doc:`click here <../internationalization/i18n>`)


Logging
~~~~~~~

* **KEY_SAVE_LOG_TO_FILE [OFF]**: enable/disable logging to file (for more details :doc:`click here <../need-help/logging>`)
* **ADMIN_SENDING_ADDRESS [issue.reporter@freedomotic.com]**: sending email address of log reports (don't change it)
* **ADMIN_RECIPIENT_ADDRESS [mauro@freedomotic.com]**: recipient address for log (don't change it if you want to send the log to the Freedomotic team)


Plugins Marketplace
~~~~~~~~~~~~~~~~~~~

* **CACHE_MARKETPLACE_ON_STARTUP [false]**: enable/disable plugins caching on startup
* **KEY_ENABLE_PLUGINS_DOWNLOAD [true]**: enable/disable plugins download from marketplace



Periodic data saving
~~~~~~~~~~~~~~~~~~~~

Basically all data are persisted when Freedomotic stopped. You can enable a periodic data saving at a fixed time interval.

* **SAVE_DATA_PERIODICALLY [false]**: enable/disable periodically data saving
* **DATA_SAVING_INTERVAL [15]**: data saving interval in minutes
   
   
Persistence
~~~~~~~~~~~

* **KEY_OVERRIDE_REACTIONS_ON_EXIT [true]**:
* **KEY_OVERRIDE_OBJECTS_ON_EXIT [true]**:


P2P
~~~

* **P2P_CLUSTER_NAME [freedomotic-commander]**: cluster name used to identify the instance in a p2p network

Resources
~~~~~~~~~

* **KEY_RESOURCES_PATH [/data/resources/]**:
* **KEY_ROOM_XML_PATH [/df28cda0-a866-11e2-9e96-0800200c9a66/df28cda0-a866-11e2-9e96-0800200c9a66.xenv]**:
   


Security
~~~~~~~~

* **KEY_ENABLE_SSO [false]**: enable/disable single sign-on for authentication
* **KEY_SECURITY_ENABLE [true]**: enable/disable authentication
