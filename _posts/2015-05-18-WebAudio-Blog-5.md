---
layout: post
title: 5. Scheduling of events
date: 2015-05-18
---
**Scheduling Web Audio with precision**
- A Tale of Two Clocks

- the two clocks: Web Audio Clock & JavaScript Clock

*Web Audio Clock*

- access to audio subsystem's hardware clock
- `currentTime` property for audio clock, floating-point number of seconds
- starting and stopping sounds, schedules changes to the sound (changing frequency or volume)
- schedules paramenters and audio events
- high-precision
- returns value in sound sample level (15 decimal digits of precision)

*JavaScript Clock*

- `Date.now()` and `setTimeout()`
- useful callback `window.setTimeout()` and `window.setInterval()` to call code back
- not very precise
- `Date.now()` returns value in milliseconds
- sensitive to other things happening on main JavaScript thread, may cause in too-immediate or delayed playback of audio files

**Scheduling methods and parameters**

- `start()` and `stop()` (previously known as `noteOn` and `noteOff`)
- Web Audio Clock: `set*ValueAtTime()` methods: `linearRampToValueAtTime()`, `exponentialRampToValueAtTime()`, `setTargetAtTime()`, `setValueCurveAtTime()`, `cancelScheduledValues`
- JavaScript Clock: `setTimeout()`, `scheduleNote()`, `nextNote()`


LINKS:

- [ArrayBuffer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer)
- [Load and decode sound files](http://www.html5rocks.com/en/tutorials/webaudio/intro/#toc-load)
- [Audio formats codec](http://en.wikipedia.org/wiki/HTML5_Audio#Supported_audio_coding_formats)
- [Media (video & audio) formats codec](https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats)
- [Audio format tests](http://hpr.dogphilosophy.net/test/)
- [A Tale of Two clocks](http://www.html5rocks.com/en/tutorials/audio/scheduling/)
