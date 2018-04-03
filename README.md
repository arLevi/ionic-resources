# ionic-resources overview
Easily **resize** your icons and splashscreens of your [Ionic project](http://ionicframework.com/).
The script replaces the existing ``ionic resources`` command which doesn't do an excellent job at the moment.

Supported OS: 
* Mac OSX, ( ``sips`` should be installed )


## Notes
* The command does **not** crop the files.
* Must run from the Ionic's root directory ( same as ``ionic resources`` command ).
* The `icon.png` in size 1024x1024 should exists under `resources/icon.png`.


## Templates
* [Splashscreen template](http://code.ionicframework.com/resources/splash.psd), minimum size of ``2208x2208``.
* Icon: no template, just make it with minimum size of ``192x192``.


## Prerequisites 
We need to prepare our environment before using ``ionic-resources``, same as written in the [official Ionic automation tutorial](http://blog.ionic.io/automating-icons-and-splash-screens/)

Execute once the ``Ionic resources`` command, this will create all the directories necessary, including adding the XML in ``config.xml``.

*Note*: if you're forcing a "landscape/portrait" orientation in the ``config.xml``, then ``ionic resources`` will generate only those images and add row for only the orientation requested.
My suggestion is to hide the ``orientation`` preference and after you're satisfied with the result - add it back.


## Usage

Create only splashscreens for the Android platform
```
ionic-resources --splash --platform android
```
  
Create only icons for both Android & iOS
```
ionic-resources --icon
```
  
Create both splashscreen & icons for the Android platform
```
ionic-resources --platform android
```

Create both icons & splashscreen for both Android & iOS
```
ionic-resources
```

### Example output
```
ionic-resources --icon

-------------------------------------------------------
        Ionic resources generator

        Requested platform(s):  Android & iOS
        Requested type(s):      Icon
 -------------------------------------------------------


Icons for Android
------------------------
--> Generating size:  48x48  ... DONE (resources/android/icon/drawable-mdpi-icon.png)
--> Generating size: 144x144 ... DONE (resources/android/icon/drawable-xxhdpi-icon.png)
--> Generating size: 512x512 ... DONE (resources/android/icon/drawable-xxxxhdpi-icon.png)
--> Generating size:  72x72  ... DONE (resources/android/icon/drawable-hdpi-icon.png)
--> Generating size:  36x36  ... DONE (resources/android/icon/drawable-ldpi-icon.png)
--> Generating size: 192x192 ... DONE (resources/android/icon/drawable-xxxhdpi-icon.png)
--> Generating size:  96x96  ... DONE (resources/android/icon/drawable-xhdpi-icon.png)

Icons for Ios
--------------------
--> Generating size:  29x29  ... DONE (resources/ios/icon/icon-small.png)
--> Generating size:  58x58  ... DONE (resources/ios/icon/icon-small@2x.png)
--> Generating size:  87x87  ... DONE (resources/ios/icon/icon-small@3x.png)
--> Generating size:  80x80  ... DONE (resources/ios/icon/icon-40@2x.png)
--> Generating size: 114x114 ... DONE (resources/ios/icon/icon@2x.png)
--> Generating size: 120x120 ... DONE (resources/ios/icon/icon-60@2x.png)
--> Generating size: 180x180 ... DONE (resources/ios/icon/icon-60@3x.png)
--> Generating size: 144x144 ... DONE (resources/ios/icon/icon-72@2x.png)
--> Generating size:  76x76  ... DONE (resources/ios/icon/icon-76.png)
--> Generating size:  57x57  ... DONE (resources/ios/icon/icon.png)
--> Generating size:  72x72  ... DONE (resources/ios/icon/icon-72.png)
--> Generating size: 100x100 ... DONE (resources/ios/icon/icon-50@2x.png)
--> Generating size:  40x40  ... DONE (resources/ios/icon/icon-40.png)
--> Generating size:  60x60  ... DONE (resources/ios/icon/icon-60.png)
--> Generating size: 152x152 ... DONE (resources/ios/icon/icon-76@2x.png)
--> Generating size:  50x50  ... DONE (resources/ios/icon/icon-50.png)

```

## Where are the files ?
After running the ``ionic-resources`` command, files will be located in:
* Android
  * Splashscreens: ``resources/android/splash``
  * Icons: ``resources/android/icon``
* iOS:
  * Splashscreens: ``resources/ios/splash``
  * Icons: ``resources/ios/icon``

Only after you ``ionic (build|emulate|run)`` the project, those files will be moved to the correct place for each platform.

