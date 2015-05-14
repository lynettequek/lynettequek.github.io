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
- `var audioContext = new AudioContext();` or `var audioContext = new (window.AudioContext || window.webkitAudioContext)();`
- connecting nodes together: the node that you want to connect is given as the argument of the connect method
- eg:
```
source = audioContext.createMediaStreamSource(stream);
source.connect(analyser);
analyser.connect(distortion);
distortion.connect(biquadFilter);
```
etc.

**OscillatorNode**

- `oscillator = audioContext.createOscillator();`
- represents an audio source generating a periodic waveform
- emits sound at time specified by `start()`


**Output of AudioNodes**

- default output is device speakers
- 
```
var audioContext = new AudioContext();
var oscillator = audioContext.createOscillator();
oscillator.connect(audioContext.destination);
```

**Parameters**

- AudioParam interface: an audio-related parameter, usually a parameter of an AudioNode
- a list of events
- can be set to a specific value or change in value, scheduled to happen at a specific time and following a specific pattern
- two kinds of AudioParam: a-rate and k-rate parameters
- `a-rate AudioParam` takes the current audio parameter value for each sample frame of the audio signal
- `k-rate AudioParam` uses the same initial audio parameter value for the whole block processed (128 sample frames)

**Attribute 1:** `frequency`

- operates in the `BiquadFilterNode`, in Hz
- default value is 350Hz
- ranges from 10Hz to half the Nyquist frequency
- 

** *Nyquist Frequency* **

- half the sample-rate

**Attribute 2:** `detune`

- parameter to modulate the speed at which the audio stream is rendered
- default value is 0
- ranges from -1200 to 1200
- 

**BiquadFilterNode:**

LINKS:

- [WebAudio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Using_Web_Audio_API)
- [AudioParam](https://developer.mozilla.org/en-US/docs/Web/API/AudioParam)
- 
