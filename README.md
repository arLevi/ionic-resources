### ionic-resources overview
Easily **resize** your icons and splashscreens of your [Ionic project](http://ionicframework.com/).

### Notes
*****
* The command does **not** crop the files.
* Must run from the Ionic's root directory ( same as ``ionic resources`` command ).
* Supporting only (.PNG) files.

### Templates
*****
* [Splashscreen template](http://code.ionicframework.com/resources/splash.psd), minimum size of ``2208x2208``.
* Icon: no template, just make it with minimum size of ``192x192``.

### Prepare your resources
*****
We need to prepare our environment before using ``ionic-resources``, same as written in the [official Ionic automation tutorial](http://blog.ionic.io/automating-icons-and-splash-screens/)

From the Ionic's root directory:
* Create our "resources" directory: ``mkdir resources``
* Copy your splash screen's file as ``resources/splash.png``
* Copy your icon's file as ``resources/icon.png``

### Usage
*****

Create only splashscreens for the Android platform
```
ionic-resources --splash --platform android
```
  
Create only icons for both Android & iOS
```
ionic-resources --icon
```
  
Create both icons & splashscreen for both Android & iOS
```
ionic-resources
```


### Where are the files ?
After running the ``ionic-resources`` command, files will be located in:
* Android
  * Splashscreens: ``resources/android/splash``
  * Icons: ``resources/android/icon``
* iOS:
  * Splashscreens: ``resources/ios/splash``
  * Icons: ``resources/ios/icon``

Only after you ``ionic (build|emulate|run)`` the project, those files will be moved to the correct place for each platform.

### Credits
*****
ionic-resources was written by the following engineers:
* Ricky Levi
