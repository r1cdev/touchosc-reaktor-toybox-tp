## Reaktor ToyBox Tangle Pack Sequencer
### Custom Built Reaktor rack and TouchOSC Template

- Instrument: Reaktor ToyBox **Tangle Pack** Sequencer, 3 tracks, 32 steps, MIDI out, Standalone
- Model: SEQ-RTP-3T32S-MS
- Version: 1.0 
- ![Static Badge](https://img.shields.io/badge/testing-in-progress-blue)


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
- [TouchOSC Connections](#touchosc-connections)
- [Requirements](#requirements)
- [Files](#files)
- [License](#license)
- [Support the Author](#support-the-author)


## Description
A TouchOSC template to control with a tablet device a **CUSTOM BUILT** Reaktor Sequencer of 3 tracks, 32 steps per track, custom built with the [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack) modular blocks. It "materializes" a well featured  "physical" sequencer in a tablet midi controller for your musical production workflow to  jam and inspire your productions.

## Operation
Reaktor runs in **standalone** mode outside of the DAW using the rack (preset) file included in the repository. The template is the midi controller, Reaktor is the sequencer instrument that can play either a virtual intrument in a DAW or a external instrument. Communication between the template and Reaktor use OSC protocol, with Reaktor being the OSC receiver. Communication between the template and a DAW use MIDI protocol, with the DAW being the Transport control and the external clock source. Clock synchronization between Reaktor and a DAW can be in 3 modes:

<div align="center"> 
<img src="images/img4.jpg" >
</div>

### Clock Mode 1: Reaktor internal Clock
In this mode Reaktor is the master clock source. Select INT as the clock source in the template. You can optionally configure Reaktor as the master clock if you want to send MIDI Clock to a DAW or a external gear. Configure your DAW or your external synthesizer or modular gear to receive and sync to a external clock source provide by Reaktor. Each DAW and external gear handles clock configuration slightly differently, so how you enable clock synchronization to a external source may require specific setup steps in each environment.

### Clock Mode 2: Ableton Link
In this mode Ableton works as the master clock source. Select EXT as the clock source in the template and enable Ableton Link in Reaktor. Enable Link in Ableton and configure your external synthesizer or modular gear to receive and sync to a external clock source provide by Ableton. Each external gear handles clock configuration slightly differently, so how you enable clock synchronization to a external source may require specific setup steps in each environment.


### Clock Mode 3: External Clock (Reason)
In this mode Reason (or any other DAW) works as the master clock source. Enable "Sync to External Clock" in Reaktor to receive clock from your DAW and enable clock send in your DAW. The template is configured to receive external clock from Reason DAW. Configure the MIDI clock sync output to use a virtual MIDI port. **Important**: This mode 3 can be used with any other DAW that can send MIDI clock sync.  Each DAW and external gear handles clock configuration slightly differently, so how you enable clock synchronization to a external source may require specific setup steps in each environment. You will also require to configure in your DAW the MIDI mapping for the transport controls (play/stop/BPM) and adjust the BPM scaling accordingly. It is already configured for Reason DAW in this template. 


### Virtual MIDI ports
A virtual midi port in your computer is needed to communicate Reaktor with your DAW. You require to configure in Reaktor the virtual MIDI ports interfaces. On a PC you can use [loopMIDI](https://www.tobias-erichsen.de/software/loopmidi.html) to create virtual ports. On a Mac, you can use the IAC bus to create any number of virtual MIDI buses. This driver can be activated in the Audio MIDI Setup Utility.


### Sync and takeover limitations
As long as your template and your DAW session are open, both are in sync. But once you close any of them, further changes will lose sync. To keep it in sync, it is recommended to manually save your template and the Reaktor rack session simultaneously before closing, to keep your session and snapshots to continue working later by recalling them. Be aware that TouchOSC does not support automatic template saving, so you must do it mannualy. Also be aware that the template uses "absolute" scaling, so you occasionally will need to move the controllers to pick up the correct value.
 
<br>

## Instrument
- Plugin: Native Instruments - Reaktor 6 
- Libraries:
	- [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack) 
	- [ToyBox Free Pack](https://www.toyboxaudio.com/pages/free-pack-details) 
	- [Reaktor Blocks Base](https://www.native-instruments.com/en/products/komplete/synths/reaktor-6/blocks/)
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
- **Snapshots:** up to 4 to store and recall sequencer values
- Link: Link changes in command values
- Clear: Initialize all values
- Reset: reset to initial position 
- Transpose: +24 to -24 interval keyboard in the template
- Mute: Mute output
- Pause: Pause sequencer
- Step: 1 step forward
- Clock: 3 modes: Internal (Reaktor), External - Ableton Link, External- Sync Clock  
- OSC return: Return control sequencer values to the template (gate, position, play)

## Reaktor rack
- Blocks: 
	- [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack) 
	- [ToyBox Free Pack](https://www.toyboxaudio.com/pages/free-pack-details) 
	- [Reaktor Blocks Base](https://www.native-instruments.com/en/products/komplete/synths/reaktor-6/blocks/)
- Rack: CUSTOM BUILT rack. Sequencer note, gate, level, ramp, counter, clock and utility modular blocks.
- Blocks Mapping: OSC  
- Reaktor OSC Configuration: 
	- OSC Activate ON 
	- Receive on Port 10000 
	- OSC Send (Identifier Target, Tablet device IP address, Port 10000)
- File: SEQ-RTP-3T32S-MS-v1_0.nksr

<div align="center"> 
<img src="images/img3.jpg" >
</div>

## TouchOSC Connections
- Reaktor Mapping: OSC
- DAW Host Mapping:  MIDI
- TouchOSC Connections 
	- MIDI Connection 1 : Send Port: Bridge, Receive Port: Bridge
	- OSC Connection 1: Host (IP of PC host), Ports: send 10000, receive 10000
	- OSC Connection 2: Host (IP of PC host), Ports: send 12101, receive 12101   (This connection required to send keystrokes)
	- Bridge: Host(IP of PC host)
- Virtual MIDI interface: Virtual midi ports on the PC/MAc to communicate Reaktor with DAW
- Physical MIDI: To communicate Reaktor with external gear

## Requirements
- Control surface software: TouchOSC
- Tablet: An iOS or Android Tablet
- DAW: (Optional) Ableton Live 11/12 or any other DAW with Send Clock. (If running in Clock mode 1 (INT), a DAW is not requiered) 
- Plugin: Native Instruments - Reaktor 6
- Reaktor Blocks: 
	- [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack) 
	- [ToyBox Free Pack](https://www.toyboxaudio.com/pages/free-pack-details) (OSC send block) 
	- Reaktor Blocks Base
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
