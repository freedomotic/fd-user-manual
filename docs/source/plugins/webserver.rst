Webserver
=========

**Description**: A modern browser based frontend for Freedomotic

**Type:**  - **Categories:** Frontend

**Development status:** Stable release

**Tested on:** All platforms

**Developer:** Gabriel Pulido de Torres

Overview
--------

This plugin serves a modern HTML5 frontend.

Configuration
-------------
* Dowload the last available 5.6 dailybuild
* Open config.xml under FREEDOMOTIC_ROOT/config and set KEY_SECURITY_ENABLE to false
* Start Freedomotic

This plugins wraps a Jetty embedded web server.

Once the plugin is running the Jetty server address is http://freedomotic_instance_ip:8090 

This server is used to be the holder of the web application client for Freedomotic.

This web application could be used to control the Freedomotic instance using any browser.

As it uses websockets, the browser needs to be a Chrome, Firefox>=10 or IExplorer>=10 (or any browser that implements the websockets feature)


Download
--------
The plugin is included inside the release package

Source code
-----------
`GitHub repository <https://github.com/freedomotic/freedomotic/tree/master/plugins/devices/webserver>`_
