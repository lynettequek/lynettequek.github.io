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
- connected via `biquadFilter.connect(audioContext.destination);`
- base for tone controls (bass, mid, treble), graphic equalizers and advanced filters
- can be combined to form complex filters
- default filter is lowpass (cutting high frequencies)
- `frequency` default value is 350Hz
- `frequency` ranges from 10Hz to half the Nyquist frequency

*Nyquist Frequency*

- half the sample-rate of a discrete signal processing system

**Properties:**

- `BiquadFilterNode.frequency`: k-rate AudioParam, representing a frequency in the current filtering algorithm (Hz)
- `BiquadFilterNode.detune`: a-rate AudioParam, representing detuning of the frequency (Cents)
- `BiquadFilterNode.Q `: k-rate AudioParam, representing a Q-factor (bandwidth - higher Q value, thinner and sharper peak. vice versa)
- `BiquadFilterNode.gain`: k-rate AudioParam, representing gain used in current filtering algorithm
- `BiquadFilterNode.type`: string value defining the kind of filtering algorithm the node is implementing

**Parameters** (type of filters)

- `lowpass`: 12dB/octave rolloff. Frequencies below cutoff passes through, frequencies above are attenuated
- `highpass`: 12dB/octave rolloff. Frequencies below cutoff are attenuated, frequencies above it pass through
- `bandpass`: Frequencies outside the given range of frequencies are attenuated, frequencies within it pass through. Width of frequency band is adjusted by Q value. Greater Q value, smaller the frequency band
- `notch`: opposite of `bandpass` filter. Frequencies outside the given range of frequencies pass through, frequencies within it are attenuated. Width of frequency band is adjusted by Q value as well
- `lowshelf`: Frequenies lower than the frequency get a boost or attenuation
- `highshelf`: Frequencies higher than the frequency get a boost or attenuation
- `peaking`: Frequencies inside the range get a boost or attenuation
- `allpass`: lets all frequencies through, changes phase-relationship between various frequencies

**Parameter Automation**

- define a mapping from time to value
- adds a new event into the list of a type specific to the method
- kept in time-order in the list
- new event will replace previous event of same type, if not it'll be placed in the list after the previous
- `setValueAtTime()` - SetValue
- `linearRampToValueAtTime()` - LinearRampToValue
- `exponentialRampToValueAtTime()` - ExponentialRampToValue
- `setTargetAtTime()` - SetTarget
- `setValueCurveAtTime()` - SetValueCurve

**Wet/Dry Connections**
CONTINUE!!!

LINKS:

- [BiquadFilterNode](https://docs.webplatform.org/wiki/apis/webaudio/BiquadFilterNode)
- [Parameters](https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode)
- [Parameter Automation](http://webaudio.github.io/web-audio-api/#audioparam-automation-example)
