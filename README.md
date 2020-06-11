# PlayerEndpoint Example

have created a library for simplifing the use of kurento-client I recommend you to take a look [lib-kurento](https://github.com/givo/lib-kurento)

## Introduction

The PlayerEndpoint example 

This is a `Node.js` example which creates a `PlayerEndpoint` to `WebRtcEndpoint` pipeline in `Kurento` media server. 

In this example a `RTSP-H.264` stream generates by `VLC` is transmitted to `Kureto` (which is deployed on Ubuntu 14.04 virtual machine) which trancodes to `VP8` and transmitted
to a simple web page in WebRTC.

## VLC

stream desktop using:

      :sout=#transcode{vcodec=h264,scale=Auto,width=1920,height=1080,acodec=mpga,ab=128,channels=2,samplerate=44100}:rtp{sdp=rtsp://:8554/v.sdp} :sout-keep
      
**Watch Out!** - using ` :file-caching` lower than 1000ms may cause image smearing and key-frame lose.

### RTSP Instructions

* Go to `media` -> `stream...`

* Then on `Capture Device` tab -> edit "Capture mode to `Desktop` and "Frame Rate" to 25 (any other framerate will be fine) and then click `next`:

![image](https://user-images.githubusercontent.com/11993599/32852472-b46b5c30-ca40-11e7-98ce-eb3bc398b6cf.png)

* Then on `Stream outpurt/Source` click `next`:

![image](https://user-images.githubusercontent.com/11993599/32852506-ce238b66-ca40-11e7-9317-f1fe5894521c.png)

* Then on `Stream output/Destination Setup` -> edit "New destination" to `RTSP`, then click `Add`:

![image](https://user-images.githubusercontent.com/11993599/32852528-e59e3f66-ca40-11e7-8fb8-07a1d3f9e103.png)

* Then edit "Destination Path" to `desktop.sdp` (any other path will be fine):

![image](https://user-images.githubusercontent.com/11993599/32852569-009649ee-ca41-11e7-905e-539fa3ac48c3.png)

* Then on "Transcoding options" click `next` and then `stream`

## Required Node.js Packages:

* async
* express
* express-session
* ws
* kurento-client
