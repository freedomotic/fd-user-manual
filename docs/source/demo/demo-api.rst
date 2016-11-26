
RestAPI
=======

Freedomotic exposes xml/json Restful API documented with Swagger.

These APIs are implemented by :doc:`RestAPIv3 <../plugins/restapiv3>` plugin.

Start Freedomotic and open in your browser the url http://localhost:9111/ to test them.

Alternatively you can try our `public demo <http://api.freedomotic.com:9111/>`_ (username: **admin**; password: **admin**)

Swagger UI Example


TODO MOVE TO DEVELOPER MANUAL

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


