---
layout: post
title: 3. Working with Effects (AudioNodes)
date: 2015-05-14
---
**GainNode**

- acts as an "audio mixer"
- represents a change in volume (volume control)
- single input and single output, multiplying the input audio signal by the `gain` attribute
- 
```
var audioContext = new AudioContext();
var gainNode = audioContext.createGain();
source.connect(gainNode);
gainNode.connect(audioContext.destination);

```

**BiquadFilterNode**

- audio processing module
- low-order filter
- created using `AudioContext.createBiquadFilter()`
- base for tone controls (bass, mid, treble), graphic equalizers and advanced filters
- can be combined to form complex filters
- default filter is lowpass (cutting high frequencies)
- `frequency` default value is 350Hz
- `frequency` ranges from 10Hz to half the Nyquist frequency

*Nyquist Frequency*

- half the sample-rate of a discrete signal processing system

LINKS:

- [BiquadFilterNode](https://docs.webplatform.org/wiki/apis/webaudio/BiquadFilterNode)
- 
