# skype-killer

A quick demo of building Skype, including video chat and text chat using OpenTok. Uses node-webkit for a Desktop App and Cordova for an iOS app

## Video Walkthrough

http://vimeo.com/112225603

## Getting Started with OpenTok

1. If you haven't already, sign up for OpenTok - Go to [www.tokbox.com](https://www.tokbox.com) and click the "Sign Up" link. 
2. Log into the Dashboard - You'll get an email after you sign up with a link to login.
3. Copy and paste your apiKey (either from the email or the "Projects" tab in the Dashboard) into the apiKey property in [index.html](index.html)
4. Generate a session ID and token and copy them into the sessionId and token properties in [index.html](index.html) - In the "Projects" tab in the Dashboard there's a form to generate these. 

## Using the WebApp

The web app lives at [index.html](index.html). You will need to run this in a web server. A simple way to do this is to use [http-server](https://www.npmjs.org/package/http-server) if you have node on your system or [SimpleHTTPServer](https://docs.python.org/2/library/simplehttpserver.html) if you have Python. 

Once you have the server running just open up index.html in 2 browser tabs and you should be able to see yourself and text chat with yourself.

## Using the Desktop App

The Desktop app lives in the [desktop](desktop/) folder. It is basically the same index.html as the WebApp except that it links to it's own copy of opentok.js just to save waiting for the download. It uses [node-webkit](https://github.com/rogerwang/node-webkit). Make sure you replace the apiKey, sessionId and token properties the same way you did for the WebApp.

To get it running you need to follow the instructions at: https://github.com/rogerwang/node-webkit

## Using the Mobile App

The mobile app uses [Apache Cordova](http://cordova.apache.org/) and the [OpenTok plugin for Cordova](https://github.com/songz/cordova-plugin-opentok) created by songz.

You will need to install the [cordova cli](https://cordova.apache.org/docs/en/3.0.0/guide_cli_index.md.html) and you will need to have XCode. Then run:

```
cd mobile
cordova plugin add https://github.com/songz/cordova-plugin-opentok/
cordova platform add ios
open platforms/ios/HelloCordova.xcodeproj
```

Then you just need to plugin an iOS device and click run. If you run into build issues have a look at the documentation at https://github.com/songz/cordova-plugin-opentok/. OpenTok iOS applications have to be run on an actual device, they don't work in the simulator unfortunately. 

Also this app works better if it's locked to portrait orientation, I didn't figure out the layout properly for landscape.
