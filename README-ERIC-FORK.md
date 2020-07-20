# H.264 support

node-webrtc is not distributed with H.264 support. You would have to build from source yourself with H.264 enabled to be able to apply this SDP.


## FORK of 0.4.6:  EvRestricted/node-webrtc:

1/ Modif of CMakeLists.txt 3 lines (cf below)

2/ Force build from source in scripts/download-prebuilt-or-build-from-source.js


Notes:
	*  use --unsafe-perm to install!
	* in Package.json  KEEP "name": "wrtc"  otw the compilation fails


```
	# libwebrtc
	# -----------------------------------------------------------------------------

	list(APPEND GN_GEN_ARGS
	  rtc_build_examples=false
	  rtc_use_x11=false
	  rtc_enable_protobuf=false
	  rtc_use_gtk=false
	  rtc_include_pulse_audio=false
	  rtc_include_tests=false
	  proprietary_codecs=true
	  ffmpeg_branding="Chrome"
	  rtc_use_h264=true
	)
```
