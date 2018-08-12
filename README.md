# sharp-image-webpack-loader
> Sharp image loader module for webpack

## Install

### npm
`$ npm install sharp-image-webpack-loader`

### yarn
`$ yarn add sharp-image-webpack-loader`

## Default Options
See (https://github.com/lovell/sharp/blob/master/lib/constructor.js).

```js
this.options = {
  // input options
  sequentialRead: false,
  limitInputPixels: Math.pow(0x3FFF, 2),
  // ICC profiles
  iccProfilePath: path.join(__dirname, 'icc') + path.sep,
  // resize options
  topOffsetPre: -1,
  leftOffsetPre: -1,
  widthPre: -1,
  heightPre: -1,
  topOffsetPost: -1,
  leftOffsetPost: -1,
  widthPost: -1,
  heightPost: -1,
  width: -1,
  height: -1,
  canvas: 'crop',
  crop: 0,
  embed: 0,
  useExifOrientation: false,
  angle: 0,
  rotateBeforePreExtract: false,
  flip: false,
  flop: false,
  extendTop: 0,
  extendBottom: 0,
  extendLeft: 0,
  extendRight: 0,
  withoutEnlargement: false,
  kernel: 'lanczos3',
  fastShrinkOnLoad: true,
  // operations
  background: [0, 0, 0, 255],
  tintA: 128,
  tintB: 128,
  flatten: false,
  negate: false,
  medianSize: 0,
  blurSigma: 0,
  sharpenSigma: 0,
  sharpenFlat: 1,
  sharpenJagged: 2,
  threshold: 0,
  thresholdGrayscale: true,
  trimTolerance: 0,
  gamma: 0,
  greyscale: false,
  normalise: 0,
  booleanBufferIn: null,
  booleanFileIn: '',
  joinChannelIn: [],
  extractChannel: -1,
  removeAlpha: false,
  colourspace: 'srgb',
  // overlay
  overlayGravity: 0,
  overlayXOffset: -1,
  overlayYOffset: -1,
  overlayTile: false,
  overlayCutout: false,
  // output
  fileOut: '',
  formatOut: 'input',
  streamOut: false,
  withMetadata: false,
  withMetadataOrientation: -1,
  resolveWithObject: false,
  // output format
  jpegQuality: 80,
  jpegProgressive: false,
  jpegChromaSubsampling: '4:2:0',
  jpegTrellisQuantisation: false,
  jpegOvershootDeringing: false,
  jpegOptimiseScans: false,
  jpegOptimiseCoding: true,
  jpegQuantisationTable: 0,
  pngProgressive: false,
  pngCompressionLevel: 9,
  pngAdaptiveFiltering: false,
  webpQuality: 80,
  webpAlphaQuality: 100,
  webpLossless: false,
  webpNearLossless: false,
  tiffQuality: 80,
  tiffCompression: 'jpeg',
  tiffPredictor: 'horizontal',
  tiffSquash: false,
  tiffXres: 1.0,
  tiffYres: 1.0,
  tileSize: 256,
  tileOverlap: 0,
  linearA: 1,
  linearB: 0,
  ...
};
```

## Usage

### Example 1
```js
const config = {
  ...
  module: {
    rules: [
      {
        test: /\.(png|jpe?g|gif|tiff)$/,
        loader: 'url-loader',
        options: {
          limit: 1000,
          name: 'images/[name].[hash:8].[ext]'
        }
      },
      {
        test: /\.(png|jpe?g|gif|tiff)$/,
        loader: 'sharp-image-webpack-loader',
        options: {
          height: 192,
          width: 192
        }
      }
    ]
  },
  ...
};
```

### Example 2
```js
const url = require('./image.jpg?width=192&height=192');
```

## Changelog
See [Changelog](./CHANGELOG.md).

## License
Copyright (c) 2018 José Massada <jose.massada@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
