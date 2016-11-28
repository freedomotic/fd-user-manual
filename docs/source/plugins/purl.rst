
pURL
====

**Description**: This reads URLs content like XML, HTML, JSON and sends it in a listenable event

**Type:** Driver - **Categories:** Network & Communication, Utilities 

**Development status:** Prototype

**Tested on:** All platforms

**Developer:** Enrico Nicoletti

Overview
--------

This plugin takes a set of urls (web services or standard web pages) from its manifest file, periodically gets their content (XML, JSON, HTML) and notifies it as a Freedomotic event. This event can be listened by the triggers shipped with this plugin (read temperature from URL, read weather from URL, ...) or you can create your own.

The triggers can be used as a data source for objects, like setting the temperature of a thermostat, or to create high level automations like

WHEN <your trigger here> THEN <say something using text to speech>
WHEN <your trigger here> THEN <send me an email>
WHEN <your trigger here> THEN <send a twitt>
WHEN <your trigger here> THEN <turn on a light>
let us know about your own triggers
 

Q: What about the plugin name?

A: The name is inspired by cURL command line linux program. http://en.wikipedia.org/wiki/CURL

Q: Where I can find example triggers?

A: As usual, they are in the data/trg folder in the plugin installation directory (freedomotic/plugins/devices/pURL/data/trg)

Q: How to reference the result of the XPATH query performed in the trigger?

A: The xpath query result is stored in property @event.url.content.xpathresult that you can use in commands. For example if you are parsing an XML content using an XPATH query to retrieve weather forecast, you can have a text to speech command like "say= Tomorrow will be @event.url.content.xpathresult" to hear "Tomorrow will be sunny"

Configuration
-------------

Actually you can just monitor a single URL changing it in the plugin manifest (menu Plugins -> Configure to edit). Detailed explanation coming when the plugin will be completed.

How to create custom triggers
-----------------------------

Create a trigger (hardware level or not) which listen to messaging channel "app.event.sensor.url". This plugins notify the following properties in the event:

url: the source of data (eg: http://www.website.com/?q=aQuery)
url.content: the XML, JSON or HTML content of the web page
url.content.length: the number of characters readed from the url (always more than zero otherwise the event is not sent)

Upcoming features
-----------------

multi url monitoring
custom polling interval for each url
username/password authentication for protected urls
XPATH feature available in freedomotic-core to do xml queries directly in your trigger (Freedomotic v5.6)