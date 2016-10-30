# debian-python-live555

Giuseppe De Marco, demarcog83 at gmail.com</br>
Mike McCandless, mikemccand at gmail.com</br>

This contains a small Python wrapper around the Live555 Streaming
Media APIs, so that you can load video frames.  It only wraps a tiny,
tiny subset of all of Live555's APIs, specifically the APIs necessary
to pull frames via RTSP/RTP from an IP camera.

Mike McCandless only tested on Linux with Python 3, with the surprisingly
excellent Lorex LNB2151/LNB2153 cameras, with H264 video.  Please
report back if you succeed with other cameras.

Giuseppe only tested with ipcam Maygion h264, not so surprising but works.

INSTRUCTIONS:

  1. First install the Live555 library from Debian repository
     aptitude install livemedia-utils liblivemedia-dev python3 python3-dev python3-pip
  
  2. Download/clone this repo

  3. then
     python3 setup.py build
     python3 setup.py install

  4. Run the example (some costants should be configured in example.py)
     python3 example.py 10.17.4.118 1 10 out.264
    
     That will record 10 seconds of H264 video from the camera at
     10.17.4.118, channel 1, saving it to the file out.264.

This forge two files: video-H264-1 and audio-PCMU-2 
openRTSP  rtsp://admin:passwd@10.87.7.10:80

Then convert it in a viewable format
...only video
ffmpeg -i video-H264-1  -acodec copy -vcodec copy -map 0:0  merged.mp4

... or video and audio
ffmpeg -i video-H264-1 -i audio-PCMU-2 -acodec copy -vcodec copy -map 0:0 -map 1:0 merged.mp4
