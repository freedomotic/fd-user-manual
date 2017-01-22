
RestAPI v3
==========

**Description**: RestAPI v3 for managing your Freedomotic instance

**Type:**  - **Categories:** API, Frontends, Networking & Communication

**Development status:** Beta version

**Tested on:** All platforms

**Developer:** Matteo Mazzoni

Overview
--------

Basic configuration
-------------------

Useful configuration parameters you can insert into your plugin manifest:

* listen-address [0.0.0.0] : the address to listen to (0.0.0.0 means every address)
* enable-ssl [true] : enables support for Secure Socket Layer
* enable-cors [true] : enables support for Cross Origin Resource Sharing

Advanced configuration
----------------------

Ports

http-port [9111] : port for plain http
https-port [9113] : port for secure http
Debugging options
debug [false] : enables debug information in console and in http headers
debug-entity [true] : when debugging, traces message payload too
SSL options
KEYSTORE_SERVER_FILE [keystore_server] : path (relative to plugin data directory) of keystore file that contains server certificates
KEYSTORE_SERVER_PWD [freedomotic] : password for certificate keystore
Cross Origin Resource Sharing options (change them very carefully!)
Access-Control-Allow-Headers
[Accept, Accept-Version, Authorization, Content-Length, Content-MD5, Content-Type, Date, Origin, X-Access-Token, X-Api-Version, X-CSRF-Token, X-File-Name, X-Requested-With] : lists allowed headers, when accessing API through XHR
Access-Control-Allow-Origin [*] : lists allowed origins for accessing API through XHR ("*" means every origin)
Access-Control-Allow-Methods [GET, POST, PUT, DELETE, HEAD] : lists allowed HTTP methods, when accessing API through XHR

Extra options
serve-static [swagger] : RestAPI plugin can serve static files in its root path. The default choice is serving SWAGGER, a API doc and tooling system
 

Usage (Documentation and tools)
-------------------------------
You can learn the API and test it, simply accessing this URL: http(s)://{listen_address}:{port}/

e.g. if using default plugin configuration, go to https://localhost:9111/

 

WebSocket endpoints documentation
/v3/ws/objectchange
When subscribed to this channel, clients will get a updated Thing (aka EnvObject) everytime any of them is modified. This is handy to keep a client updated without polling data.

/v3/ws/zonechange
When subscribed to this channel, clients will get a updated Zone when its boundaries are changed

/v3/ws/pluginchange
When subscribed to this channel, clients will get a updated Plugin data when it is started/stopped or its configuration changes.
 

Try API with cURL
-----------------

You can test API using the commandline tool cURL

Command format is

.. code:: 

   curl --user <username>:<password> http://<listen_address>:<port>/v3/<API>

For example if you want to retrieve the users' list on our online demo authenticated as admin please digit

.. code::

   curl --user admin:admin http://api.freedomotic.com/9111/v3/users 

