
Messaging system
================

Through messaging system travels Events, Triggers and Commands.

Events
######

Events are notification of facts like "the state of an hardware device is changed", "the user have clicked an object on the GUI" or "an
object changes its behavior from ON to OFF". They can be published by any component of the system, a sensor, a frontend, the core
itself...

Triggers
########

Triggers listen for events and filter they values (EVENT: "the user have clicked an object" -> TRIGGER: "if living-room light is clicked")

Commands
########
Commands are instructions to do something like "turn on living-room light".

Reactions (aka Automations)
###########################

Reactions bounds trigger and commands to create an automation: "if living-room light is clicked" THEN "turn on living-room light"
