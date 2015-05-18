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

**Playing sounds**

- `playSound()` - called every time a key is pressed or mouse is clicked
- `start(time)` - function to schedule precise sound playback for games and applications

*ArrayBuffer*
- a generic fixed-length container for binary data (bytes)

LINKS:

- [ArrayBuffer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer)
