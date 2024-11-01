## Reaktor ToyBox Tangle Pack Sequencer TouchOSC template
- Instrument: Reaktor ToyBox **Tangle Pack** Sequencer, 3 tracks, 32 steps, MIDI out, Standalone
- Model: SEQ-RTP-3T32S-MS
- Version: 1.0 
- ![Static Badge](https://img.shields.io/badge/testing-progress-blue)


<div align="center"> 
<img src="images/img1.gif" >
</div>

## Description
A TouchOSC template to control a Reaktor 3 tracks 32 STEPS Sequencer virtual instrument, using ToyBox Tangle Pack modular blocks which can be used to jam and inspire your productions. It "materializes" a well featured  "physical" sequencer for your musical production workflow.

## Instrument
- Plugin: Native Instruments - Reaktor 6 
- Library: [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack)
- Main Modules: Sequencers, Utility
- Operation Mode:  Standalone
- DAW Host:  Any DAW that supports virtual MIDI inputs

## Sequencer
- Tracks: 3 tracks 
- Steps: 32 steps per track, melodic sequencer
- MIDI out: Pitch, gate (with velocity level)
- Modulation: Velocity, Gate time, Shuffle
- 8 Sequencer modes: 
	- fwd  
	- rev  
	- fwd-rev 
	- tri
	- patt1
	- patt2
	- rand
	- glitch
- **Snapshots:** 4 to store and recall playing sequencer values
- Clear: Initialize all values
- Reset: reset to initial position 
- Transpose: pitch track using an external midi controller
- Mute: Mute output
- Pause: Pause sequencer
- Step: 1 step forward
- Clock: Internal (Reaktor), External - Ableton Link  External- Sync Clock  
- OSC out: to send control and step signals to template

## Reaktor rack
- Blocks: ToyBox Tangle Pack

<div align="center"> 
<img src="images/img3.jpg" >
</div>

## Connections
- Reaktor Mapping: OSC
- DAW Host Mapping:  MIDI
- TouchOSC Connections 
	- MIDI: Bridge
	- OSC: Host (IP of PC host), Ports: send 10000, receive 10000
	- Bridge: Host(IP of PC host)

## Requirements
- Control surface software: TouchOSC
- Tablet: An iOS or Android Tablet
- DAW: Any DAW that supports virtual MIDI inpupts
- Plugin: Native Instruments - Reaktor 6
- Reaktor Modular Blocks: ToyBox Tangle Pack
- Target virtual instrument: Any virtual instrument in your DAW
- Target external instrument:  Any external midi instrument 
- Optional external MIDI controller: For pitch transpose

## License

<a href= https://github.com/murry61/touchosc-reaktor-8steps/blob/main/LICENSE > <img alt="GitHub License" src="https://img.shields.io/github/license/murry61/touchosc-reaktor-8steps"></a>

All assets and code are under the MIT LICENSE in the public domain unless specified otherwise.

---

## Support the Author
<p> 
I'm passionate about creating code that brings joy, inspiration, and creativity into people's lives. If you've enjoyed what I share and want to support my work, your contribution will help me to continue building. Every little bit fuels my creativity.
</p>

**_Thank you for your kindness and support!_** 

<a href="https://www.buymeacoffee.com/r1c4rd0" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 41px !important;width: 174px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>
