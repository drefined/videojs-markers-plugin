## Forked from https://github.com/spchuang/videojs-markers for 1.0.2 NPM release
## Not actively maintained

Video.js Markers Plugin - works with Video.js 7.6
===================
![Alt text](https://raw.github.com/fealaer/videojs-markers-plugin/master/screenshot.png "Screen shot of videojs.markers.plugin")

A plugin that displays customizable markers upon progress bars of the video with [Video.js](https://github.com/videojs/video.js/). This could be used to show video breaks and show overlaid text on the video when playback reaches the specific break point.

## Demo and Documentation
JSBin Demo can be found [here](https://codepen.io/fealaer/pen/RwbKeye)

## Features
* Display markers on progress bar, with hover-over tooltips
* Display break overlays
* Flexible styling
* Support dynamically adding and removing markers

## Download

* Install as npm - `yarn add videojs-markers-plugin` or `npm install videojs-markers-plugin`
* Install as bower package -- `bower install videojs-markers-plugin`

## Download

* Download master with git -- `git clone git@github.com:fealaer/videojs-markers-plugin.git`
* Download zip/tar files for newest release

## Quick Start
Add the 'videojs.markers.plugin.js' plugin and stylesheet after including videojs script

    <link href="http://vjs.zencdn.net/4.2/video-js.css" rel="stylesheet">
    <link href="videojs.markers.plugin.css" rel="stylesheet">
    <script src="http://vjs.zencdn.net/4.2/video.js"></script>
    <script src='../src/videojs.markers.plugin.js'></script>

### Basic usage: display break markers in the video.
To add breaks in the video, simply add a new time (in seconds) in the list of breaks option.

    // initialize video.js
    var video = videojs('test_video');

    //load the marker plugin
    video.markers({
      markers: [
         {time: 9.5, text: "this"},
         {time: 16,  text: "is"},
         {time: 23.6,text: "so"},
         {time: 28,  text: "cool"}
      ]
    });

### Customize marker style:
The style of the markers could be modified by passing an optional setting "markerStyle" with your preference of css styles.

    video.markers({
      markerStyle: {
         'width':'8px',
         'background-color': 'red'
      },
      markers: [
         {time: 9.5, text: "this"},
         {time: 16,  text: "is"},
         {time: 23.6,text: "so"},
         {time: 28,  text: "cool"}
      ]    
    });

## Development
```
> git clone https://github.com/fealaer/videojs-markers-plugin
> cd videojs-markers-plugin
> npm install

// compile js/css assets
// install grunt: https://gruntjs.com/getting-started
> npm install -g grunt-cli
> grunt compile
```

## History
- 1.0.3
   - Fix marker positioning when the stream is live and the ui is enabled
- 1.0.2
   - Fix deprecation warnings for latest version of Video.js (6.8.x)
   - Allow html to be specified for markerTip
- 1.0.1
   - fix /dist missing issue (issue 81)
- 1.0.0
   - add force flag in updateTime
   - small bug fixes including UI bug (https://github.com/spchuang/videojs-markers/pull/79)
- 0.9.0
   - remove jquery dependency
- 0.7.0
   - support videojs 5
- 0.6.0
   - add index parameter to `onMarkerReached`
   - fix bugs where video crashes when played the second time
   - break overlay uses `html` instead of `test`
   - added babel && flow
- 0.5.0
   - add 'onMarkerClick' callback handler. When this returns false, the default behavior of seeking to the marker time will be prevented.
   - add new 'getMarkers' API
   - remove constraints of using 'time' as the marker time attribute. Instead, a new markertip.time() function is added to resolve the time dynamically. This mean the time attribute can be represented in different attributes. This also made marker times modifiable (see new demo file). Note that the UI position of the marker will only be updated after you call marker.players.updateTime().
- 0.4
   - change display_time to displayTime
   - markers now takes an array of object containing time, text, overlay text
   - add markerReached callback
   - markerTip and overlay text is now a clalback function for higher flexibility
   - Add many markers APIs for adding and removing markers dynamically.
- 0.1
   - initial release

## License
This project is licensed under MIT.
