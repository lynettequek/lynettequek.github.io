---
layout: post
title: 4. Load and decode audio files (AudioBufferSourceNode)
date: 2015-05-18
---
**Loading audio files**

- uses `AudioBuffer` for short to medium-length sounds
- `XMLHttpRequest` is used to fetch sound files
- audio files can be in any format supported by the `audio` element (eg. wav, mp3, aac, varies on different browsers as well)
- `var request = new XMLHttpRequest();`
- `request.open('GET', url, true);`
- `request.responseType = 'arraybuffer';` - as audio file data is binary, `responseType` is set to `arraybuffer`

**Decoding audio files**

- `decodeAudioData`
- decodes audio file data contained in `ArrayBuffer`, loaded from an XMLHttpRequest `request.response` attribute
- `audioData`: ArrayButter containing audio file data
- `successCallback`is invoked when decoding is finished, representing the decoded PCM audio data
- `errorCallback` is invoked if there is an erro decoding the audio file data
- decoded PCM audio data is represented as an `AudioBuffer`
- asynchronously decodes the audio file

**Playing sounds**

- `playSound()` - called every time a key is pressed or mouse is clicked
- `start(time)` - function to schedule precise sound playback for games and applications

*ArrayBuffer*
- a generic fixed-length container for binary data (bytes)

**Codec support**
- audio coding formats supported by the `audio` element, on various browsers

- Google Chrome: *ogg, vorbis, wav, pcm, mp3, aac, opus*
- Internet Explorer: *mp3, aac*
- Mozilla Firefox: *ogg, vorbis, wav, pcm, mp3, aac, opus*
- Opera: *ogg, vorbis, wav, pcm, mp3, aac, opus*
- Safari: *wav, pcm, mp3, aac*

**One-shot behaviour**

- an `AudioBufferSourceNode` acts one-shot, only executes once when called
- create new one once it has been `.start()` and `.stop()`

LINKS:

- [ArrayBuffer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer)
- [Load and decode sound files](http://www.html5rocks.com/en/tutorials/webaudio/intro/#toc-load)
- [Audio formats codec](http://en.wikipedia.org/wiki/HTML5_Audio#Supported_audio_coding_formats)
- [Media (video & audio) formats codec](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats)
- [Audio format tests](http://hpr.dogphilosophy.net/test/)
