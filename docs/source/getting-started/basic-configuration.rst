Basic configuration
===================

All the configuration parameters are included in the file *FREEDOMOTIC_ROOT/config/config.xml*.


Basic
~~~~~

* **KEY_BROKER_URL [vm\://localhost?persistent\=false]**:
* **KEY_MESSAGES_TTL [5000]**:
* **KEY_ENABLE_SSO [false]**:
* **KEY_SHOW_WEBSITE_ON_STARTUP [false]**:
* **KEY_DISCARD_INVALID_DESTINATIONS [true]**:
* **P2P_CLUSTER_NAME [freedomotic-commander]**:
* **KEY_COLORED_PEOPLE [false]**:
* **KEY_JAVACOM_LIB [../ext]**:


Internationalization
~~~~~~~~~~~~~~~~~~~~

* **KEY_ENABLE_I18N [auto]**:


Logging
~~~~~~~

* **KEY_SAVE_LOG_TO_FILE [OFF]**:
* **ADMIN_SENDING_ADDRESS [issue.reporter@freedomotic.com]**:
* **ADMIN_RECIPIENT_ADDRESS [mauro@freedomotic.com]**:


Plugins Marketplace
~~~~~~~~~~~~~~~~~~~

* **CACHE_MARKETPLACE_ON_STARTUP [false]**:
* **KEY_ENABLE_PLUGINS_DOWNLOAD [true]**:



Periodic data saving
~~~~~~~~~~~~~~~~~~~~

Basically all data are persisted when Freedomotic stopped. You can enable a periodic data saving at a fixed time interval.

* **SAVE_DATA_PERIODICALLY [false]**: enable/disable periodically data saving
* **DATA_SAVING_INTERVAL [15]**: data saving interval in minutes
   
   
Persistence
~~~~~~~~~~~

* **KEY_OVERRIDE_REACTIONS_ON_EXIT [true]**:
* **KEY_OVERRIDE_OBJECTS_ON_EXIT [true]**:

Resources
~~~~~~~~~

* **KEY_RESOURCES_PATH [/data/resources/]**:
* **KEY_ROOM_XML_PATH [/df28cda0-a866-11e2-9e96-0800200c9a66/df28cda0-a866-11e2-9e96-0800200c9a66.xenv]**:
   


Security
~~~~~~~~

* **KEY_SECURITY_ENABLE [true]**: