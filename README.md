# ionic-resources overview
Easily **resize** your icons and splashscreens of your [Ionic project](http://ionicframework.com/).
The script replaces the existing ``ionic resources`` command.

Supported OS: 
* Mac OSX, ( ``sips`` should be installed )


## Notes
* The command does **not** crop the files.
* Must run from the Ionic's root directory ( same as ``ionic resources`` command ).
* Supporting only (.PNG) files.


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


## Where are the files ?
After running the ``ionic-resources`` command, files will be located in:
* Android
  * Splashscreens: ``resources/android/splash``
  * Icons: ``resources/android/icon``
* iOS:
  * Splashscreens: ``resources/ios/splash``
  * Icons: ``resources/ios/icon``

Only after you ``ionic (build|emulate|run)`` the project, those files will be moved to the correct place for each platform.

