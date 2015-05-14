---
layout: post
title: 1. Getting started with WebAudio
date: 2015-05-14
---

**Definitions**

**API**: Application Programming Interface.

- A set of routines, protocols, and tools for building software applications

**HTML**: HyperText Markup Language.

- Provides a standard for playing audio files
- Important methods: load(), play(), pause()
- Important attributes: autoplay, controls, loop, muted, preload, src
- 
```
< audio> 
```
tag specifies a standard way to embed audio in a web page

**JavaScript**: A dynamic programming language, object-oriented, commonly used to create interactive effects within web browsers.

- embedded in HTML, within <script> tags

**AudioContext**: Managing and playing all sounds

- AudioContext connects sound sources to the sound destination
- Only needed once for each audio application created
- Executes the audio processing or decoding
- Contains AudioNodes
- 
```
var audioContext = new AudioContext()
```

**AudioNodes**: Processing modules for audio signal

- Performs basic audio operations
- Linked via inputs and outputs chain
- Contains effects eg. Filters, Reverb, Delay

- *Audio Sources Nodes*
- 
```
OscillatorNode, AudioBuffer, AudioBufferSourceNode, MediaElecmentAudioSourceNode, MediaStreamAudioSourceNode
```
- *Audio Effects Nodes*
- 
```
BiquadFilterNode, ConvolverNode, DelayNode, DynamicsCompressorNode, GainNode, StereoPannerNode, WaveShaperNode, PeriodicWave
```
- *Audio Destinations*
- 
```
AudioDestinationNode, MediaStreamAudioDestinationNode
```

LINKS:
[HTML Audio Tag](http://www.w3schools.com/htmL/html5_audio.asp)
[AudioContext](http://www.html5rocks.com/en/tutorials/webaudio/intro/)
[WebAudio Interfaces](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)

