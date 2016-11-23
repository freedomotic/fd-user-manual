
FAQ
===

What platforms are supported?
-----------------------------
Freedomotic can run on any OS with Java support (Linux, Windows, Mac, …).

Can I run Freedomotic on Raspberry Pi?
--------------------------------------
Sure, follow :doc:`these instructions<../getting-started/installation>` 

What version of Java do I need to run Freedomotic?
--------------------------------------------------
Freedomotic can run on JDK version 7+.

What tecnologies / tools are used?
----------------------------------
Freedomotic adopts open source tecnologies for development and project management.

I need help. How?
-----------------
First of all consult this documentation. If you are a developer you can subscribe our technical mailing list (https://groups.google.com/forum/#!forum/freedom-domotics)

Can I use Freedomotic in commercial projects?
---------------------------------------------
Yes you can, and we encourage it!

Freedomotic is released under GNU GPL 2 license, both for core and for java plugins so any right/restriction of this license is applied. You can even sell Freeedomotic copies or get paid to develop plugins for third parties. You can also fork Freedomotic, modify it and sell it. About this last case if you have some use cases that are not currently covered, before forking the project we suggest to start a discussion and let us know your needs, this way we can plan the implementation of new features into freedomotic-core and maintain the development effort on a single direction. You can partecipate in first person to change the freedomotic-core if you want it, we are glad to have new core developers. However the plugins system allows you to extend Freedomotic in a very flexible/powerful way, also using not Java languages, so rarely core changes are needed, even for complex extensions.

How to run Freedomotic headless (server mode with no GUI)
---------------------------------------------------------
In Freedomotic also GUIs are plugins. Freedomotic is shipped with a basic desktop GUI plugin installed into *FREEDOMOTIC_ROOT/plugins/devices/frontend-java* folder. Just move the **frontend-java** folder away from there and restart Freedomotic without any GUI.
