
Rest API
========

Freedomotic exposes xml/json Restful API documented with Swagger.

These APIs are implemented by Restapi-v3 plugin, refer to http://freedomotic.com/content/plugins/restapi-v3 for further information.

Start Freedomotic on your localhost and go to http://localhost:9111/ to test them live.

Or you can try our public demo API (username: admin; password: admin)

Swagger UI Example

Advanced topics
###############
When developers need to interface directly to the message broker (NOT NECESSARY FOR EVERYDAY OPERATIONS), the following methods are available

Stomp - message broker connector
********************************
STOMP (Streaming Text Oriented Messaging Protocol): Download from here the STOMP client for your preferred language http://stomp.github.com//implementations.html. Freedomotic has a STOMP endpoint active on IP: 0.0.0.0 PORT:61666

Websockets - message broker connector
*************************************
Freedomotic has a websocket endpoint - covering the active on IP:0.0.0.0 PORT:61614

TODO: add further info


