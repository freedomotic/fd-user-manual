
Telegram Bot
============

**Description**: This plugin interacts with a Telegram Bot

**Type:** Driver - **Categories:** Access Control & Security, Social 

**Development status:** Prototype

**Tested on:** All platforms

**Developer:** Mauro Cicolella

Overview
--------


Configuration
-------------

Create a bot
~~~~~~~~~~~~

You have to talk to another Bot, called **The BotFather**. You can start a conversation with the BotFather using this `link <https://telegram.me/botfather>`_.

Once you’ve followed the prompt to start interacting with the bot, send the ``/newbot`` command to begin the interactive bot-creation process.

First of all the BotFather asks a name for your bot. This is the friendly name displayed when the bot speaks to you. You can choose anything you like.

Then you need to pick a username. Telegram forces all bots to have a username that ends with ‘bot’. This is how you’ll add the bot to Telegram to begin interacting with it. You might, for example, name your bot “MyName’s Bot” and select "MyNameBot" as username.

Once you’ve picked a name and a username, the BotFather will reply with your bot’s token. 

That’s all! Your bot is ready to work.

Start a chat and find its ID
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To send a message through the Telegram bot API, you have to provide the ID of the chat with your bot.

So start a conversation with your bot with ``/start``. Then open in your browser the url https://api.telegram.org/bot$TOKEN/getUpdates where **$TOKEN** is the key provided by the BotFather in previous step. 

You'd see a JSON response like the following (if needed go to page source in your browser):

.. code::

 {"ok":true,
  "result":[
   {"update_id":123123123,
    "message":{
      "message_id":12,
      "from":{
        "id":12345,
        "first_name":"Bob",
        "last_name":"Jones",
        "username":"bjones"},
      "chat":{
        "id":12345,
        "first_name":"Bob",
        "last_name":"Jones",
        "username":"bjones",
        "type":"private"},
      "date":1452933785,
      "text":"Hi there, bot!"}}]}

The chatID is 12345 in this example.


Plugin configuration
~~~~~~~~~~~~~~~~~~~~

Open the *telegram-bot-manifest.xml* and set your bot's **token**, **username** and **chatID**.

Then start the plugin.

Create an automation example
----------------------------

* Right click on an object
* Switch to Automations tab
* In the field ``when OBJECT_NAME object is clicked`` write this command ``Notify event by Telegram``
* Save changes
* When you click on this object you should receive a notification on your Telegram client with the following predefined message "Event notified: @event.description"

Soon we'll add more examples and info about messages customization.

.. note:: The plugin is not completed. If you want to follow the development and contribute or submit your comments please go to https://github.com/freedomotic/freedomotic/issues/224