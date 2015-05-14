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
- <audio> tag specifies a standard way to embed audio in a web page
- Important methods: load(), play(), pause()
- Important attributes: autoplay, controls, loop, muted, preload, src

**JavaScript**: A dynamic programming language, object-oriented, commonly used to create interactive effects within web browsers.
- embedded in HTML, within <script> tags

**AudioContext**: Managing and playing all sounds
- AudioContext connects sound sources to the sound destination
- Only needed once for each audio application created
- Contains AudioNodes
```
var audioContext = new AudioContext()
```

**AudioNodes**: Processing modules for audio signal

LINKS:
[HTML Audio Tag](http://www.w3schools.com/htmL/html5_audio.asp)
[AudioContext](http://www.html5rocks.com/en/tutorials/webaudio/intro/)

