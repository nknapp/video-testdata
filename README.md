This module contains test video-files that can be used to test video-conversion
to different formats.

## Usage

Syntax: `require("video-testdata")("<filename>",["<innerFile>"], callback(err,file)`

The callback-parameter `file` contains the path to the requested file (see below).
If the file is a tar-file, it is automatically extracted and `file` will point to
a temporary directory containing the extracted data.
If the file is a tar-file, a `innerFile` may be provided. `file` will then point to
this file within the extracted tar-file.


```js
require("video-testdata")("<filename>",function(err, file) {
    // do something
});

// ... or, for tar-files ...

require("video-testdata")("<tar-filename>","<inside-file>",function(err, file) {
    // do something
});

// ... or,

require("video-testdata")("<tar-filename>",function(err, directory) {
    // do something
});


// If you are not using a tar-file, you can also do
var file = require.resolve("video-testdata/data/<filename>");
```

## Files

The following files can be used

#### `0-novideo.mp4`

This file is not actually a video but a text file containing "123". Can be used as "broken" video"

#### `1-video-streamable.mp4`

An mp4-video with H264/AAC streams with the "moov" box near the beginning, so that ffmpeg can
perform a streaming decode

#### `2-video-unstreamable.mp4`

An mp4-video with H264/AAC streams with the "moov" box not near the beginning, so that ffmpeg does not
accept this video via stdin.

#### `panasonic-lumix-dmc-zx3.tar`

A tar-file containing the sd-card content of Panasonic Lumix after recording a single video.
In particular, the inner file `PRIVATE/AVCHD/BDMV/STREAM/00000.MTS` is a AVHCD MPEG2-Transport-
Stream file.

#### `samsung-smx-f40bp-edc.tar`

A tar-file containing the sd-card content of Samsung-Camcorder after recording a single video.
In particular, the inner file `VIDEO/100VIDEO/SDV_0999.MP4` is a mp4-file.

