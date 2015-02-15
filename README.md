This module contains test video-files that can be used to test video-conversion
to different formats.

require.resolve("video-testdata/data/0-novideo.mp4")
----------------------------------------
This file is not actually a video but a text file containing "123". Can be used as "broken" video"

require.resolve("video-testdata/1-video-streamable.mp4")
--------------------------------------
An mp4-video with H264/AAC streams with the "moov" box near the beginning, so that ffmpeg can
perform a streaming decode

require.resolve("video-testdata/data/2-video-unstreamable.mp4")
--------------------------------------
An mp4-video with H264/AAC streams with the "moov" box not near the beginning, so that ffmpeg does not
accept this video via stdin.

require.resolve("video-testdata/data/panasonic-lumix-dmc-zx3.tar")
-------------------------------------------------------
A tar-file containing the sd-card content of Panasonic Lumix after recording a single video.

require.resolve("video-testdata/data/samsung-smx-f40bp-edc.tar")
-------------------------------------------------------
A tar-file containing the sd-card content of Samsung-Camcorder after recording a single video.

