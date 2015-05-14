---
layout: post
title: 2. WebAudio with Oscillators
date: 2015-05-14
---
**AudioNodes**: Processing modules for audio signal

- Performs basic audio operations
- Linked via inputs and outputs chain
- Contains effects eg. Filters, Reverb, Delay
- *Audio Sources Nodes*:
```
OscillatorNode, AudioBuffer, AudioBufferSourceNode, MediaElecmentAudioSourceNode, MediaStreamAudioSourceNode
```
- *Audio Effects Nodes*:
```
BiquadFilterNode, ConvolverNode, DelayNode, DynamicsCompressorNode, GainNode, StereoPannerNode, WaveShaperNode, PeriodicWave
```
- *Audio Destinations*:
```
AudioDestinationNode, MediaStreamAudioDestinationNode
```

**Connecting AudioNodes**

- first create AudioContext to build the audio graph (linkage of AudioNodes)
- provide versions for different browsers 
- 
```javascript
var audioContext = new AudioContext();
or 
var audioContext = new (window.AudioContext || window.webkitAudioContext)();
```
- connecting nodes together: the node that you want to connect is given as the argument of the connect method
- eg:
```javascript
source = audioContext.createMediaStreamSource(stream);
source.connect(analyser);
analyser.connect(distortion);
distortion.connect(biquadFilter);
etc.
```


**OscillatorNode**

- 
```
oscillator = audioContext.createOscillator();
```

**Output of AudioNodes**

- default output is device speakers
- 
```
var audioContext = new AudioContext();
var oscillator = audioContext.createOscillator();
oscillator.connect(audioContext.destination);
```

LINKS:

- [WebAudio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)
- 
