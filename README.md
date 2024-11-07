## Reaktor ToyBox Tangle Pack Sequencer TouchOSC template
- Instrument: Reaktor ToyBox **Tangle Pack** Sequencer, 3 tracks, 32 steps, MIDI out, Standalone
- Model: SEQ-RTP-3T32S-MS
- Version: 1.0 
- ![Static Badge](https://img.shields.io/badge/testing-progress-blue)


<div align="center"> 
<img src="images/img1.gif" >
</div>


## Contents
- [Description](#description)
- [Operation](#operation)
- [User Guide](USER_GUIDE.md)
- [Instrument](#instrument)
- [Sequencer](#sequencer)
- [Reaktor rack](#reaktor-rack)
- [Connections](#connections)
- [Requirements](#requirements)
- [Files](#files)
- [License](#license)
- [Support the Author](#support-the-author)


## Description
A TouchOSC template to control a Reaktor 3 tracks 32 STEPS Sequencer virtual instrument, using the [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack) modular blocks. It "materializes" a well featured  "physical" sequencer for your musical production workflow to  jam and inspire your productions.

## Operation
The template is  with Reaktor running in standalone mode outside of your DAW using the rack (preset) file included in the repository, with clock synchronization in 3 modes:

<div align="center"> 
<img src="images/img4.gif" >
</div>

### Clock Mode 1: Reaktor internal Clock
In this mode Reaktor works as the master clock source. Select INT as the clock source in the template and send MIDI Clock to MIDI output in Reaktor. Configure your DAW or your external synthesizer or modular gear to receive and sync to a external clock source provide by Reaktor. Each DAW and external gear handles clock configuration slightly differently, so how you enable clock synchronization to a external source may require specific setup steps in each environment.

### Clock Mode 2: Ableton Link
In this mode Ableton works as the master clock source. Select EXT as the clock source in the template and enable Ableton Link in Reaktor. Enable Link in Ableton and configure your external synthesizer or modular gear to receive and sync to a external clock source provide by Ableton. Each external gear handles clock configuration slightly differently, so how you enable clock synchronization to a external source may require specific setup steps in each environment.


### Clock Mode 3: External Clock (Reason)
Enable "Sync to External Clock" in Reaktor to receive clock from your DAW and enable clock send in your DAW. The template is configured to receive external clock from a Reason DAW. Configure the MIDI clock sync output to use a virtual MIDI port. This mode 3 can be used with any DAW that can send MIDI clock sync.  Each DAW and external gear handles clock configuration slightly differently, so how you enable clock synchronization to a external source may require specific setup steps in each environment. You will also need to configure in your DAW the MIDI mapping for the transport controls (play/stop/BPM) and adjust the BPM scaling accordingly (already configured for Reason DAW in this template). 


### Virtual MIDI ports
Run a virtual midi port in your computer to communicate Reaktor with your DAW (loopMIDI recommended) and do the necessary midi port configurations and routing. If you use the template with external gear, configure en Reaktor the MIDI ports interfaces you use. 


### Sync and takeover limitations
As long as your template and your DAW session are open, both are in sync. But once you close any of them, further changes will lose sync. To keep it in sync, it is recommended to manually save your template and DAW session simultaneously before closing, to keep your session and snapshots to continue working later by recalling them. Be aware that TouchOSC does not support automatic template saving, so you must do it mannualy. Also be aware that the template uses "absolute" scaling, so you occasionally will need to move the controllers to pick up the correct value.


 
<br>

## Instrument
- Plugin: Native Instruments - Reaktor 6 
- Library: [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack)
- Main Modules: Sequencers, Utility
- Operation Mode:  Standalone
- DAW Host:  Any DAW
- MIDI: Virtual MIDI port 

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
- Link: Link changes in snapshot. clear, reset, transport, mute, pause
- Clear: Initialize all values
- Reset: reset to initial position 
- Transpose: pitch track using an external midi controller
- Mute: Mute output
- Pause: Pause sequencer
- Step: 1 step forward
- Clock: Internal (Reaktor), External - Ableton Link  External- Sync Clock  
- OSC out: to send control and step signals to template
- MIDI out: 3 MIDI ports to send sequences through virtual midi ports to DAW

## Reaktor rack
- Blocks: ToyBox Tangle Pack
- Rack: Author designed rack with note, gate, level, ramp, counter, clock and utility modular blocks.  
- File: SEQ-RTP-3T32S-MS-v1_0.nksr

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
- MIDI: Virtual midi ports to connect Reaktor with DAW

## Requirements
- Control surface software: TouchOSC
- Tablet: An iOS or Android Tablet
- DAW: Any DAW that supports virtual MIDI inpupts
- Plugin: Native Instruments - Reaktor 6
- Reaktor Modular Blocks: ToyBox Tangle Pack
- Target virtual instrument: Any virtual instrument in your DAW
- Target external instrument:  Any external midi instrument
- MIDI: Virtual MIDI ports

## Files 
- TouchOSC template: SEQ-RTP-3T32S-MS-v1.0.tosc
- Reaktor rack:      SEQ-RTP-3T32S-MS-v1_0.nksr

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
