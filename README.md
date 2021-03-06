# d3.js Face Detection Plugin

A d3.js plugin to detect faces on images (both HTML and SVG), videos and canvases to get their coordinates.

**Importante note:** This plugin uses an algorithm by [Liu Liu](http://liuliu.me/).

This is a fork of the very popular [jquery.facedetection](http://facedetection.jaysalvat.com) by [jaysalvat](https://github.com/jaysalvat)

## Get started

Download the plugin with the method of your choice.

- Download the [last release](https://github.com/nicksrandall/d3.facedetection/zipball/master) manually
- Or install it with [Bower](http://bower.io/).

```
bower install d3.facedetection
```

- Or install it with [NPM](https://www.npmjs.org/package/d3.facedetection).

```
npm install d3.facedetection
```

Include [d3](https://github.com/mbostock/d3/releases/download/v3.5.3/d3.zip) and the plugin.

```html
<script src="//cdnjs.cloudflare.com/ajax/libs/d3/3.5.3/d3.min.js"></script> 
<script src="path/to/dist/d3.facedetection.min.js"></script> 
```

Set a picture with some faces in your HTML (or SVG) page.

```html
<svg height="350px" width="620px" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink= "http://www.w3.org/1999/xlink">
  <image id="picture" xlink:href="picture.jpg" x="0" y="0" width="620px" height="350px"></image>
</svg>
```
Apply the plugin to this image and get the face coordinates.

```html
<script>
    d3.select('#picture').faceDetection({
        complete: function (faces) {
            console.log(faces);
        }
    });
</script> 
```

## Results

Returns an array of found faces object:

- **x** — Y coord of the face in the picture
- **y** — Y coord of the face in the picture
- **width** — Width of the face
- **height** — Height of the face
- **positionX** — X position relative to the document
- **positionY** — Y position relative to the document
- **offsetX** — X position relative to the offset parent
- **offsetY** — Y position relative to the offset parent
- **scaleX** — Ratio between original image width and displayed width
- **scaleY** — Ratio between original image height and displayed height
- **confidence** — Level of confidence

## Settings
- **interval** — Interval (default 4)
- **minNeighbors** — Minimum neighbors threshold which sets the cutoff level for discarding rectangle groups as face (default 1)
- **confidence** — Minimum confidence (default null)
- **async** — Async mode if Worker available (default false). The async mode uses Workers and needs the script to be on the same domain.
- **grayscale** — Convert to grayscale before processing (default true)
- **complete** — Callback function trigged after the detection is completed

```js
complete: function (faces) {
    // ...
}
```

- **error** — Callback function trigged on errors

```js
error: function (code, message) {
    // ...
}
```
