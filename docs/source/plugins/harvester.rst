Harvester
=========

**Description**: Collects events in a db, for data analysis and much more

**Type:** Driver - **Categories:** Utilities 

**Development status:** Prototype

**Tested on:** All platforms

**Developer:** Matteo Mazzoni

Overview
--------
If you need to collect events, this plugin is what you are looking for.

Features:

* Filter events based on Trigger mechanism
* Sample configuration for major dbms, including Mysql, MSQL, H2, Sqlite
* Easily support almost any dbms

Configuration
-------------

.. note:: Users running JAVA1.7 and up, must add a vm option when running Freedomotic in order to workaround a known issue with OpenJPA and ClassLoader. Option is:  -XX:+AlwaysLockClassLoader

Post installation steps:

* edit harvester-manifest.xml, to select your db type
* edit _YOUR_DB_TYPE_.xml to properly configure it
* restart Freedomotic

Usage
=====
In order to save an event on db you have to 'intercept' it. This is easy with the built-in Reaction mechanism in Freedomotic.

A basic Reaction is provided alongside the plugin, and it is made up by:

* A trigger, "When a object changes its status"
* A command "Save event on Harvester"
* A reaction that links the elements above

You could made your custom trigger, and link it to the "Save event on Harvester" command in order to put on db other kinds of data.

