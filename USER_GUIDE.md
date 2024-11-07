## Reaktor ToyBox Tangle Pack Sequencer TouchOSC template

## USER GUIDE

## Contents
- [Transport](#transport)
- [Control](#controls)
- [Sequencer](#sequencer)


## Transport

<div align="center"> 
<img src="images/img5.jpg" with=70% >
</div>

### INT/EXT CLOCK
Allows you to select Internal or External clock source. The Play/Stops controls change accordingly and the BPM values scales. If you select EXT, two options are enabled: Ableton Link and Reason. If you use other external DAW instead of Reason, you can do it, but you need to change the BPM scale values inthe script to match the values and scales in your DAW. 

### BPM
Select de beats per minute in either REAKTOR (INT) or your external DAW (EXT). You will need to MIDI map mannualy the BPM control in your DAW and match the scale. (Reason DAW is already configured). BPM is the same for all 3 sequencers.

### Play / Stop
Play and stop all 3 sequencers. It has 3 modes of operation, depending on the selected clock source:

- **INT** clock mode: PLAY/STOP are already OSC mapped to the Reaktor rack. 

- **EXT** CLock - **Ableton Link** : First you will need to midi map this controls to your DAW. Two play buttons are avalilable in this mode, one for Reaktor and one for Ableton. Reaktor can play or stop independent of Ableton, but is linked in beat, phase and tempo to the master clock of Ableton. (But Ableton can start the playing in Reaktor if the Sync option is selected in the midi output ports settings). In this mode Reaktor does not have a modular block to control the start/stop control inside the rack. Play/stop control works with a space bar message whis is sent by the template, but it requires the "focus" on the Reaktor window to work. Unfortunately this is a limitation that you will need to take into account. A stream deck will easy the workflow to work it. 

- **EXT** Clock - **Reason** (Or other external DAW): First you will need to midi map this controls to your DAW. One play/stop button is available, that is mapped to your DAW. The DAW has the transport control and it start and stop the transport in Reaktor. 

<div align="center"> 
<img src="images/img8.jpg" with=70% >
</div>

### Mute 
Mute the selected track (all 3 if LINK selected). The sequencer steps continue running, but without MIDI output

### Reset
Reset the track position to the start on the selected track (all 3 if LINK selected). The start position is 1 or the last step, depending on the sequqncer direction mode. 

### Pause
Pause the selected track (all 3 if LINK selected). The sequencer steps stops, and no MIDI output. The internal ramp generator continue running, and it will continue on a future step when finshing the pause. 

### Step 
Advance one step the selected track (all 3 if LINK selected). This is useful to test your sequence.  


## Control

<div align="center"> 
<img src="images/img6.jpg" with=70% >
</div>

### Snapshots
The template supports the snapshot (preset) functionality, that allows you to save and recall up to four configurations per sequencer: note, gate, velocity and controls ( gate rate, shuffle, gate time, mode and steps). MIDI channel does not change with each snapshot. Each time you select a snapshot,  it automatically changes the value in the Reaktor file. But be aware it is no bidirectional, that means, if you change a value in the Reaktor rack, it will not be updated to the template. The template acts as the "master" configuration. If you want to start from zero, just run press the CLEAR button with the LINK enabled to clear the values at once in the 3 sequencers and repeat that for each snapshot. 

### Link
The LINK (L) button, links several commands, that allows you to execute it simultaneously on the 3 sequencers. The commands that works with the "LINK" feature are: SNAPSHOT, CLEAR, NOTE, TRANSP, MUTE, RESET, PAUSE, and STEP. Just press the L button and it will color in orange the "linked" controls. 

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

### Clear
Initializes the values of the sequencer track (all 3 if LINK selected) to a starting values of: gate = all selected, note = C3, velocity = 100, Gate Rate = 4th, Shuffle = 0%, Gate Time = 50, Mode = FWD, Steps = 32. 

### Note display and zoom
Display the pitch values of each step, displayed on the top of each step gate button. That will easy to setup the note values of each step. The zoom button on the right, extends the faders to input the pitch values, and meke it more easy an confortable to slide the faders. 

### Transpose
The template has included a -24+24 interval keyboard to transpose, to make it easy to transpose each sequencer track (all 3 if LINK selected), without the need of an external midi controller. It displays the transpose interval according to the key pressed, being C3 the central key. It is displayed or hidden when you press the Transp control. 

<div align="center"> 
<img src="images/img9.jpg" with=70% >
</div>


## Sequencer

<div align="center"> 
<img src="images/img7.jpg" with=70% >
</div>

### Gate section
Select each step to play it or not. It can be changed an any time and its value is stored automatically in the corresponding snapshot. But remember to mannualy save the template if you close it to keep the values. Depending on the number of steps selected, the gate steps can be displayed or hidden. 

### Note (Pitch) section
Select the value of the note on each step. It can be changed at any time and its value is stored automatically in the corresponding snapshot. But remember to mannualy save the template if you close it to keep the values. Depending on the number of steps selected, the note steps can be displayed or hidden. The note value that you change in the fader can be displayed when you press the Note button. If you press the zoom button, the note faders are expanded and you can more easily move it to setup your note values. 

### Velocity section
Select the value of the velocity (volume level) on each steps. It works only if your instrument support velocity control. It can be changed at any time and its value is stored automatically in the corresponding snapshot. But remember to mannualy save the template if you close it to keep the values. Depending on the number of steps selected, the velocity steps can be displayed or hidden. The velocity value that you change in the fader can be displayed automatically over the note group. 

