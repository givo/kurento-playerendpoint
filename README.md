# PlayerEndpoint Example

## Introduction

The PlayerEndpoint example 

This is a `Node.js` example which creates a `RtpEndpint` to `WebRtcEndpoint` pipeline in `Kurento` media server. 

In this example a `h.264` stream generates by `Haivision Makito DVI` is transmitted to `Kureto` (which is deployed on Ubuntu 14.04 virtual machine) which trancodes to `VP8` and transmitted to a simple web page in WebRTC.

## Required Node.js Packages:

* async
* express
* express-session
* ws
* kurento-client
