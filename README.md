## Reaktor ToyBox Tangle Pack Sequencer TouchOSC template
- Instrument: Reaktor ToyBox **Tangle Pack** Sequencer, 3 tracks, 32 steps, MIDI out, Standalone
- Model: SEQ-RTP-3T32S-MS
- Version: 1.0 
- ![Static Badge](https://img.shields.io/badge/testing-progress-blue)


<div align="center"> 
<img src="images/img1.gif" >
</div>

## Description
A TouchOSC template to control a Reaktor 3 tracks 32 STEPS Sequencer virtual instrument, using ToyBox Tangle Pack modular blocks. It "materializes" a well featured  "physical" sequencer for your musical production workflow to  jam and inspire your productions.

## Operation
The template is  with Reaktor running in standalone mode outside of your DAW using the rack (preset) file included in the repository, with clock synchronization in 3 modes:

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


## Controls


### INT/EXT
Allows you to select Internal or External clock source. The Play/Stops controls change accordingly and the BPM values scales. If you select EXT, two options are enabled: Ableton Link and Reason. If you use other external DAW instead of Reason, you can do it, but you need to change the BPM scale values inthe script to match the values and scales in your DAW. 

### BPM
Select de beats per minute in either REAKTOR (INT) or your external DAW (EXT). You will need to MIDI map mannualy the BPM control in your DAW and match the scale. (Reason DAW is already configured). 

### Play / Stop
- INT clock mode: PLAY/STOP are already OSC mapped to the Reaktor rack. 

- EXT CLock - Ableton Link: First you will need to midi map this controls to your DAW. Two play buttons are avalilable in this mode, one for Reaktor and one for Ableton. Reaktor can play or stop independent of Ableton, but is linked in beat, phase and tempo to the master clock of Ableton. (But Ableton can start the playing in Reaktor if the Sync option is selected in the midi output ports settings). In this mode Reaktor does not have a modular block to control the start/stop control inside the rack. Play/stop control works with a space bar message whis is sent by the template, but it requires the "focus" on the Reaktor window to work. Unfortunately this is a limitation that you will need to take into account. A stream deck will easy the workflow to work it. 

- EXT Clock - Reason (Or other external DAW): First you will need to midi map this controls to your DAW. One play/stop button is available, that is mapped to your DAW. The DAW has the transport control and it start and stop the transport in Reaktor. 

### Snapshots
The template supports the snapshot (preset) functionality, that allows you to save and recall up to four configurations per sequencer: note, gate, velocity and modulation controls. Each time you select a snapshot,  it automatically changes the value in the Reaktor file. But be aware it is no bidirectional, that means, if you change a value in the Reaktor rack, it will not be updated to the template. The template acts as the "master" configuration. If you want to start from zero, just run press the CLEAR button with the LINK enabled to clear the values at once in the 3 sequencers and repeat that for each snapshot. 

### Link
The LINK (L) button, links several commands, that allows you to execute it simultaneously on the 3 sequencers. The commands that works with the "LINK" feature are: SNAPSHOT, CLEAR, NOTE, TRANSP, MUTE, RESET, PAUSE, and STEP. Just press the L button and it will color in orange the "linked" controls. 


### Clear
Initializes the values of the sequencer track (all 3 if LINK selected) to a starting values of: gate = all selected, note = C3, velocity = 100, Gate Rate = 4th, Shuffle = 0%, Gate Time = 50, Mode = FWD, Steps = 32. 


### Note display and zoom
Display the pitch values of each step, displayed on the top of each step gate button. That will easy to setup the note values of each step. The zoom button on the right, extends the faders to input the pitch values, and meke it more easy an confortable to slide the faders. 

### Transpose
The template has included a -24+24 interval keyboard to transpose, to make it easy to transpose each sequencer track (all 3 if LINK selected), without the need of an external midi controller. It displays the transpose interval according to the key pressed, being C3 the central key. It is displayed or hidden when you press the Transp control. 

### Mute 
Mute the selected track (all 3 if LINK selected). The sequencer steps continue running, but without MIDI output


### Reset
Reset the track position to the start on the selected track (all 3 if LINK selected). The start position is 1 or the last step, depending on the sequqncer direction mode. 

### Pause
Pause the selected track (all 3 if LINK selected). The sequencer steps stops, and no MIDI output. The internal ramp generator continue running, and it will continue on a future step when finshing the pause. 

### Step 
Advance one step the selected track (all 3 if LINK selected). This is useful to test your sequence.  

### Gate Rate
Select the gate rate of each track: 4th, 8th, 16th, 32th and 64th.


### Shuffle
Select a shuffle of each track to introduce cariations in the rythm.

### Gate Time
Select a gate time of each track.

### Mode
Select one of the 8 sequencer modes: FWD, REV, FWD-REV, TRI, PATT1, PATT2, RAND, GLITCH. 

### Channel
Select the midi output channel for each sequencer track. Take care to use a midi channel that is not used by any other instrument and use a virtual MIDI port in your computer, that is not used or reserved by other DAW or applications. loopMIDI is a good option that allows you to create any number of virtual ports that you need.

### Steps
Select the number of steps for each sequencer track, that can be up to 32 steps. The steps that are not used, change to a hidden state in the template, so you have a visual feedback of the steps available. 

### Gate section
Select each step to play it or not. It can be changed an any time and its value is stored automatically in the corresponding snapshot. But remember to mannualy save the template if you close it to keep the values. Depending on the number of steps selected, the gate steps can be displayed or hidden. 

### Note (Pitch) section
Select the value of the note on each step. It can be changed at any time and its value is stored automatically in the corresponding snapshot. But remember to mannualy save the template if you close it to keep the values. Depending on the number of steps selected, the note steps can be displayed or hidden. The note value that you change in the fader can be displayed when you press the Note button. If you press the zoom button, the note faders are expanded and you can more easily move it to setup your note values. 

### Velocity section
Select the value of the velocity (volume level) on each steps. It works only if your instrument support velocity control. It can be changed at any time and its value is stored automatically in the corresponding snapshot. But remember to mannualy save the template if you close it to keep the values. Depending on the number of steps selected, the velocity steps can be displayed or hidden. The velocity value that you change in the fader can be displayed automatically over the note group. 


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
