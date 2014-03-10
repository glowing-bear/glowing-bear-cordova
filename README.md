glowing-bear-cordova
====================

Native app for glowing-bear, the HTML5 irc client of the 21st century. Android, for now.


Setup
-----

First, you need to get the glowing-bear submodule:

`git submodule init && git submodule update`

Secondly, check out the wonderful https://github.com/creationix/nvm if you don't know it already, it's highly recommended.

Then, install cordova:

`npm install -g cordova`

Next, you need to have cordova generate all the necessary build files that aren't checked into git:

`cordova platform update android`

Now you are ready to build! Type `cordova build` to build. Your apk file will end up in the
`/platforms/android/ant-build/` folder.

Some other commands you might want to have a look at are `cordova emulate` to build and install in an Android emulator instance, or `cordova run` to build and install onto a device (or an emulator). You can also have a look at http://www.ng-newsletter.com/posts/angular-on-mobile.html#native for some more information.

