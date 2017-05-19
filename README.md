# debian-python-live555
Giuseppe De Marco, demarcog83 at gmail.com</br>

forked from </br>
https://pypi.python.org/pypi/live555/1.0</br>
Mike McCandless, mikemccand at gmail.com</br>

This contains a small Python3 wrapper around the Live555 Streaming
Media APIs, so that you can load video frames.  It only wraps a tiny,
tiny subset of all of Live555's APIs, specifically the APIs necessary
to pull frames via RTSP/RTP from an IP camera.

<b>Mike McCandless</b> tested on Linux with the surprisingly
excellent <b>Lorex LNB2151/LNB2153</b> cameras, with H264 video.  
<b>I</b> only tested with ipcam <b>Maygion h264</b>, not so surprising as camera but works.

INSTRUCTIONS:

  1. First install the Live555 library from Debian repository</br>
     <b>aptitude install livemedia-utils liblivemedia-dev python3 python3-dev python3-pip</b>
  
  2. Download/clone this repo

  3. then</br>
     <b>python3 setup.py build</b>
     <b>python3 setup.py install</b>

  4. Run the example (some costants should be configured in example.py)</br>
     <b>python3 example.py 10.17.4.118 1 10 out.264</b>
    
     That will record 10 seconds of H264 video from the camera at</br>
     10.17.4.118, channel 1, saving it to the file out.264.

Some alternative methods with live555 and ffmpeg
================================================

<b>openRTSP -4 -y -P 300 -F output rtsp://admin:passwd@10.87.7.10:80</b></br>
will output 5-min mp4 chunks.

=====================================
<b>vlc -I dummy rtsp://admin:passwdk@10.87.7.10:80 --sout=file/ts:mystream.mpg</b>

