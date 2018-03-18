glowing-bear-cordova
====================

Native app for glowing-bear, the HTML5 irc client of the 21st century.

Supports Android and iOS (self-deploy only).

You can install the developer preview from the Google Play Store [here](https://play.google.com/store/apps/details?id=com.glowing_bear).

Getting started
---------------

After cloning this repository, you will need to get the glowing-bear submodule:

`git submodule init && git submodule update`

Secondly, check out the wonderful [nvm](https://github.com/creationix/nvm) if you don't know it already, it's highly recommended.

Then, install cordova:

`npm install -g cordova`

Next, you need to have cordova generate all the necessary build files that aren't checked into git:

```bash
cordova platform add android
```

Lastly you need to tell cordova to get all of the plugins we use, and then you'll be ready to build!

```bash
cordova plugin restore
```

Building for Android
--------------------

Type `cordova build android` to build. Your apk file will end up in the
`/platforms/android/build/outputs/apk/debug` folder.

Some other commands you might want to have a look at are `cordova emulate` to build and install in an Android emulator instance, or `cordova run` to build and install onto a device (or an emulator). You can also have a look at http://www.ng-newsletter.com/posts/angular-on-mobile.html#native for some more information.

Building for iOS
----------------
Due to licensing issues, Glowing Bear (probably) can't be published on Apple's App store. Fortunately, you can self-deploy apps to your phone for free (!) as of iOS 9 / Xcode 7.

First, add the platform:

```bash
cordova platform add ios
```

Then install all the plugins with `cordova plugin restore` as above.

Next, open the generated `Glowing Bear.xcodeproj` in Xcode. You'll need to change the Bundle Identifier to something unique to get the code signing to work. Otherwise, the default Bundle Identifier will only work in the emulator. Then, follow the steps at http://bouk.co/blog/sideload-iphone/ to deploy it to your physical device.

**Note:** As the Cordova build includes a copy of the GB source, it won't auto update. You'll need to update, recompile, and redeploy to get any new features of Glowing Bear.

Generating Splash Screen / Icons
--------------------------------
Two high-res "template" pngs have been included in `icons\` -- `icon.png` and `splash.png`. From these, a variety of icons and splash screens can be generated for the various platforms, without having to manually create each one. Install `splashicon-generator` from npm and ensure you have ImageMagick installed.


```bash
npm install splashicon-generator -g
```

Then run it from the root project directory, pointing it to the `icons\` directory:

```bash
splashicon-generator --imagespath=icons/
```

See the documentation for `splashicon-generator` at https://github.com/eberlitz/splashicon-generator , including how to set up `config.xml` for various platforms.



Debugging
---------

You should be able to debug a connected Android device or a running emulator using [Chrome's Remote Debugging feature](https://developers.google.com/chrome-developer-tools/docs/remote-debugging).
