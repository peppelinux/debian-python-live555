# debian-python-live555

Giuseppe De Marco, demarcog83 at gmail.com__
Mike McCandless, mikemccand at gmail.com__

This contains a small Python wrapper around the Live555 Streaming
Media APIs, so that you can load video frames.  It only wraps a tiny,
tiny subset of all of Live555's APIs, specifically the APIs necessary
to pull frames via RTSP/RTP from an IP camera.

Mike McCandless, only tested on Linux with Python 3, with the surprisingly
excellent Lorex LNB2151/LNB2153 cameras, with H264 video.  Please
report back if you succeed with other cameras.

Giuseppe only tested with ipcam Maygion h264

INSTRUCTIONS:

  * First install the Live555 library from Debian repository
    aptitude install livemedia-utils liblivemedia-dev python3 python3-dev python3-pip

  * then
    python3 setup.py build__
    python3 setup.py install__ 

  * Run the example
    python3 example.py 10.17.4.118 1 10 out.264
    
    That will record 10 seconds of H264 video from the camera at
    10.17.4.118, channel 1, saving it to the file out.264.
