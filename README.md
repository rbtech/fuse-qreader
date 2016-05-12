Fuse Qreader
============

Library qr code scanner for [Fuse](http://www.fusetools.com/).

This library is adaptation (the structure and code base) of Fuse Gallery (https://github.com/bolav/fuse-gallery)
The QR Code reader is using built iOS framework and the code is based on sample code by Yannick Loriot (https://github.com/yannickl/QRCodeReaderViewController)

The android version is based on google vision sample that use Google Vision API (Part of Google Play Service library) (https://github.com/googlesamples/android-vision)


## Installation

## Build

For android , the fuse build will result error (I'm not sure why but it's questioning '@style\Theme.AppCompat' in AndroidManifest.xml), but you can open and build the project with the android studio and it should be work just fine. Don't forget to install Google Play Service, Google Support Library and NDK before build the project.

## Usage

UX:

```
<Qreader ux:Global="Qreader" />
<Text Value="{txt}">
```

JavaScript:

```
var qreader = require('Qreader');
var Observable = require('FuseJS/Observable');
var txt = Observable();

function load () {
 qreader.scan().then(function (res) {
  txt.value = res;
 });
}
module.exports = {
 load: load,
 txt: txt
}
```
