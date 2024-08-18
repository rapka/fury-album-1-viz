# Fury Album 1 Visualizer

This is a fork of my React/HTML5 based [music visualizer](https://github.com/rapka/spin-viz), customized for the [artwork](https://www.youtube.com/watch?v=4olse9eXdbk) to my 2024 album [Fury - 34 Minutes of Fury]
(https://collegehill.bandcamp.com/album/34-minutes-of-fury).


## Setup

```
nvm use
npm ci
npm start
```

Once running, your browser should automatically open to [http://localhost:3000](http://localhost:3000).

Use the spacebar to being playback. There's currently no support for pausing and replaying a song requires a page refresh.

## Configuration

The app is configured via `src/config/config.json`. It follows the following format:

```
{
	"artist": "Fury",
	"album": "34 Minutes Of",
	"title": "Down",
	"mix": "Sober Mix ",
	"track": "12 Go Out With A (Remastered).wav",
	"videoSrc": "34_minutes_video_final_small.mp4",
	"invert": true,
	"noise": false
}
```

The `mix` field corresponts to the vertical text used to desribe the

Images and audio files should be placed in `/public`.

### Background

Backgrounds can be any valid CSS color or a background image. If `css` is set, it will be used as the CSS `background` shorthand and will override the values for `color` and `image`.

If `loopDuration` is set, its value will determine how long it takes for the background image to loop horizontally (in seconds). the `vertical` flag will make the image move from top to bottom instead of left to right.

### Colors

By default, a waveform will be drawn for each color in `colors`. Colors can be any valid CSS value, excluding the trailing semicolon.

If `rotationOffset` is set, the waveform will change colors, going through the rainbow. In this case, the hues of each waveform in `colors[]` are replaced and separated from each other by the value of `rotationOffset` in degrees. For example, ` { "rotationOffset": 0, colors: ["#FFF", "#FFF"] }` will render two waveforms that begin as red and green respectively.

### Artwork

In addition to the background image, an additional foreground image can be configured in the `art` field. If `rotationDuration` is set, its value will determine how long is takes for the image to spin in seconds. The `backwards` flag will make the image spin counter-clockwise and `blendMode` determines the [CSS blend mode](https://developer.mozilla.org/en-US/docs/Web/CSS/mix-blend-mode)
 used on the image.

