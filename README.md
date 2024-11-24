## Reaktor ToyBox Tangle Pack Sequencer
### TouchOSC template for a custom built Reaktor rack sequencer

- Instrument: Reaktor [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack) Sequencer, 3 tracks, 32 steps, MIDI
- Model: TBT-332
- Version: 1.0 
- ![Release](https://img.shields.io/github/v/release/r1cdev/touchosc-reaktor-toybox-tp)

<div align="center"> 
<img src="images/img1.gif" >
</div>


## Contents
- [Description](#description)
- [Operation](#operation)
- [User Guide :link: ](USER_GUIDE.md)
- [Instrument](#instrument)
- [Sequencer](#sequencer)
- [Reaktor rack](#reaktor-rack)
- [TouchOSC Connections](#touchosc-connections)
- [Requirements](#requirements)
- [Download](#download)
- [License](#license)
- [Support the Author](#support-the-author)


## Description
A TouchOSC template to control and play with a tablet device a **custom built** Reaktor 3 tracks, 32 steps sequencer, using the [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack) modular blocks. It "materializes" a physical sequencer in a tablet device for your musical production workflow to jam and inspire your productions.

## Operation
Reaktor runs in **standalone** mode outside of a DAW using the custom-built rack (preset) file included in the repository. You can play either a virtual instrument in your DAW or play an external instrument with midi. Communication between the template and a Reaktor use OSC protocol. Communication between the template and a DAW use MIDI protocol. Clock synchronization can be selected in 3 modes:

<div align="center"> 
<img src="images/img4.jpg" >
</div>

### Clock Mode 1: Reaktor internal Clock
Reaktor is the master clock source. Select INT as the clock source in the template. You can optionally configure Reaktor as the master clock if you want to send MIDI Clock to a DAW or an external gear. Configure your DAW or your external synthesizer or modular gear to receive and sync to an external clock source provided by Reaktor. Each DAW and external gear handles clock configuration slightly differently, so how you enable clock synchronization to an external source may require specific setup steps in each environment.

### Clock Mode 2: Ableton Link
Ableton Link is the master clock source. Toggle INT and select Link as the clock source in the template. Enable Ableton Link in both Ableton and Reaktor. Configure your external synthesizer or modular gear to receive and sync to an external clock source provided by Ableton. Each external gear handles clock configuration slightly differently, so how you enable clock synchronization to a external source may require specific setup steps in each environment. Configure in Ableton the MIDI mapping for the transport controls (play/stop/BPM) and adjust the BPM scaling from 20 to 240.


### Clock Mode 3: External Clock (Reason)
Reason (or any other DAW) is the master clock source. Toggle INT and select EXT as the clock source in the template. Enable "Sync to External Clock" in Reaktor to receive clock from your DAW and enable clock send in your DAW. Configure the MIDI clock sync output to use a virtual MIDI port. **Important**: Mode 3 can be used with any other DAW provided it can send MIDI clock sync signal.  Each DAW and external gear handles clock configuration slightly differently, so how you enable clock synchronization to an external source may require specific setup steps in each environment. Configure in your DAW the MIDI mapping for the transport controls (play/stop/BPM) and adjust the BPM scaling accordingly. BPM scale is already configured for Reason DAW in the template side. 


### Virtual MIDI ports
Use a virtual midi port in your computer to communicate Reaktor with your DAW. On a PC you can use [loopMIDI](https://www.tobias-erichsen.de/software/loopmidi.html). On a Mac, you can use the IAC bus to create any number of virtual MIDI buses. This driver can be activated in the Audio MIDI Setup Utility.


### Snapshot sync and midi takeover
If your template and your Reaktor session are open, the sequencer values and snapshots are in sync. But once you close any of them, further separate changes will lose sync. To keep both in sync, it is recommended to manually save your template and the Reaktor rack session simultaneously before closing and recall them later to continue working. Be aware that TouchOSC does not support automatic template saving, so you must do it manually. The template uses "absolute" scaling, so you occasionally will need to move the controllers to pick up the correct value. 
 
<br>

## Instrument
- Instrument: **Custom built** 3 tracks, 32 steps sequencer
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
- Link: Link changes in control values
- Clear: Initialize values
- Reset: Reset to start position 
- Transpose: +24 to -24 interval keyboard
- Mute: Mute midi output
- Pause: Pause sequencer
- Step: 1 step forward
- Clock: 3 modes: Internal (Reaktor), External - Ableton Link, External - Clock Sync  
- OSC return: Return control sequencer values to the template (position, gate, play status)

## Reaktor rack
- Custom Built Rack: Modular sequencer blocks: note, gate, level, ramp, counter, clock and utility.
- Blocks: 
	- [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack) 
	- [ToyBox Free Pack](https://www.toyboxaudio.com/pages/free-pack-details) 
	- [Reaktor Blocks Base](https://www.native-instruments.com/en/products/komplete/synths/reaktor-6/blocks/)
- Blocks Mapping: OSC  
- Reaktor OSC Configuration: 
	- OSC Activate ON 
	- Receive on Port 10000 
	- OSC Send (Identifier Target, Tablet device IP address, Port 10000)
- Rack File: TBT-332-v1.0.nksr

<div align="center"> 
<img src="images/img3.jpg" >
</div>

## TouchOSC Connections
- Reaktor Mapping: OSC (already mapped)
- DAW Host Mapping:  MIDI 
- Tablet device TouchOSC Connections: 
	- MIDI Connection 1: Send Port: Bridge, Receive Port: Bridge
	- OSC Connection 1: Host (IP of PC host), Ports: send 10000, receive 10000
	- OSC Connection 2: Host (IP of PC host), Ports: send 12101, receive 12101 (OSC send keystrokes)
	- Bridge: Host (IP of PC host)
- Virtual MIDI interface: Virtual midi ports on the PC or Mac to communicate Reaktor with DAW
- Physical MIDI: To communicate Reaktor with external gear
- Instructions: See [How to Set Up TouchOSC with Reaktor](https://support.native-instruments.com/hc/en-us/articles/4408082499345-How-to-Set-Up-TouchOSC-with-Reaktor) in Native Instruments support site. 

## Requirements
- Control surface software: TouchOSC
- Tablet: An iOS or Android Tablet
- DAW (Optional): Ableton Live 11/12 or any other DAW with Send Clock feature. (Only required for clock modes 2 and 3) 
- Plugin: Native Instruments - Reaktor 6
- Reaktor Blocks: 
	- [ToyBox Tangle Pack](https://www.toyboxaudio.com/pages/tangle-pack) 
	- [ToyBox Free Pack](https://www.toyboxaudio.com/pages/free-pack-details) (OSC send block) 
	- [Reaktor Blocks Base](https://www.native-instruments.com/en/products/komplete/synths/reaktor-6/blocks/)
- Target virtual instrument: Any virtual instrument in your DAW
- Target external instrument:  Any external midi instrument
- MIDI: Virtual MIDI ports

## Download
Download the following files to use the template:
- TouchOSC template: [TBT-332-v1.0.tosc](files/TBT-332-v1.0.tosc)
- Reaktor rack:      [TBT-332-v1_0.nksr](files/TBT-332-v1_0.nksr)

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
