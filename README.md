glowing-bear-cordova
====================

Native app for glowing-bear, the HTML5 irc client of the 21st century. Android, for now.

You can install the developer preview from the Google Play Store [here](https://play.google.com/store/apps/details?id=com.glowing_bear)

Getting started
---------------

After cloning this repository, you will need to get the glowing-bear submodule:

`git submodule init && git submodule update`

Secondly, check out the wonderful [nvm](https://github.com/creationix/nvm) if you don't know it already, it's highly recommended.

Then, install cordova:

`npm install -g cordova`

Next, you need to have cordova generate all the necessary build files that aren't checked into git:

`cordova platform update android`
`cordova platform update firefoxos`

Don't worry about the errors it will spew at you (if you insist on having them disappear, just run the command again. It won't change anything, but this time around, no errors should be found).

Lastly you need to tell cordova about the plugins we use, and then you'll be ready to build!

```bash
cordova plugin add cordova-plugin-inappbrowser
cordova plugin add cordova-plugin-splashscreen
cordova plugin add de.appplant.cordova.plugin.local-notification
```

Building for Android
--------------------

Type `cordova build android` to build. Your apk file will end up in the
`/platforms/android/build/outputs/apk/` folder.

Some other commands you might want to have a look at are `cordova emulate` to build and install in an Android emulator instance, or `cordova run` to build and install onto a device (or an emulator). You can also have a look at http://www.ng-newsletter.com/posts/angular-on-mobile.html#native for some more information.

Building for FirefoxOS
----------------------

As FirefoxOS apps are pure web apps, a simple `cordova prepare firefoxos` suffices to copy all the necessary files to the correct places. You can then point your Firefox to `about:app-manager` and add `platforms/firefoxos/www` as a packaged app. Done! If you want to learn more, https://hacks.mozilla.org/2014/02/building-cordova-apps-for-firefox-os/ is a great starting point.

Debugging
---------

If you want to attach the browser's debugger, you need to tell Cordova to enable debugging. Do so with `cordova plugin add com.jamiestarke.webviewdebug`
