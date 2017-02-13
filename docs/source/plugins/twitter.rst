
Twitter4Freedomotic
===================

**Description**: Makes your home post messages on Twitter social network

**Type:**  - **Categories:** Social

**Development status:** Stable release

**Tested on:** All platforms

**Developer:** Gabriel Pulido de Torres

Overview
--------

This plugin allows Freedomotic to publish messages, as status updates, on Twitter.
A Twitter account is required to be configured to allow an external application status post messages.

Configuration
-------------
This plugin post messages on a twitter account so it needs to know the OAuth parameters to connect to your twitter account.

The following parameters have to be defined in the xml that you can find under *FREEDOMOTIC_ROOT_FOLDER/plugin/devices/twitter/twitter-actuator.xml*.

.. csv-table:: 
   :header: "Parameter", "Required", "Values"
   :widths: 15, 10, 60

   "OAuthConsumerKey","yes","see next section "How to obtain the OAuth parameters"
   "OAuthConsumerSecret","yes","see next section "How to obtain the OAuth parameters"
   "OAuthAccessToken","yes","see next section "How to obtain the OAuth parameters"
   "OAuthAccessTokenSecret","yes","see next section "How to obtain the OAuth parameters"

How to obtain the OAuth parameters
----------------------------------

* Create an account on Twitter that it is going to publish Freedom messages. It's recommended **NOT TO USE** your own but another as "house account". Maintain it private, and only accept users by invitation (if not, all persons could see your Freedomotic messages).
Now we have to obtain the **ConsumerKey** and **ConsumerSecret** for this application. In Twitter, login with the new user, and go to https://dev.twitter.com/apps. Register the app that is going to be used. (configure it as read&write in the Settings page)
login to https://dev.twitter.com/apps with your new twitter "house account"

* Click on "create an application". Fill the form with Name: Freedomotic ; Description: Twitter plugin for freedom building automation; Website: http://freedomotic.com; Application Type: Read&write; the rest can be left empty. Accept twitter rules, fill the captcha, click on "Create your twitter application"

* Now click on your application name and switch to tab "OAuth Tool": we have obtained the ConsumerKey and the ConsumerSecret values.

* Now we have to obtain the AccessToken and the AccessTokenSecret. In the plugin jar is included a java executable: OAuthSetup

* Execute it in a terminal, paste the ConsumerKey and the ConsumerSecret. In output you obtain an url.

* Paste the url in a browser to obtain a Code.

* Copy and paste that code in the commandline where OAuthSetup is being executing. After OAuthSetup gives you the AccessToken? and AccessTokenSecret.

* Fill the twitter-actuator.xml with this 4 values (substitute them in the included example of xml) and your twitter plugin is configured.

.. code:: xml

 <config>
    <properties>
        <property name="description"            value="Actuator for Twitter"/>
        <property name="version"                value="40"/>
        <property name="required"               value="40"/>
        <property name="category"               value="Twitter4Freedom"/>
        <property name="short-name"             value="TwitterActuator"/>
        <property name="OAuthConsumerKey"       value="**PASTE OAuthConsumerKey HERE**"/>
        <property name="OAuthConsumerSecret"    value="**PASTE OAuthConsumerSecret HERE**"/>
        <property name="OAuthAccessToken"       value="**PASTE OAuthAccessToken HERE**"/>
        <property name="OAuthAccessTokenSecret" value="**PASTE OAuthAccessTokenSecret HERE**"/>
    </properties>
 </config>
