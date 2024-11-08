## Reaktor ToyBox Tangle Pack Sequencer TouchOSC template

## USER GUIDE

## Contents
- [Transport](#transport)
- [Control](#controls)
- [Sequencer](#sequencer)
- [MIDI Setup](#midi-setup)
- [OSC Setup](#osc-setup)

## Transport

<div align="center"> 
<img src="images/img5.jpg" with=70% >
</div>

### INT/EXT CLOCK
Allows you to select Internal or External clock source. The Play/Stops controls change accordingly and the BPM values scales. If you select EXT, two options are enabled: Ableton Link and Reason. If you use other external DAW instead of Reason, you can do it, but you need to change the BPM scale values inthe script to match the values and scales in your DAW. 

<div align="center"> 
<img src="images/img8.jpg" with=70% >
</div>

### BPM
Select de beats per minute in either REAKTOR (INT) or your external DAW (EXT). You will need to midi map mannualy the BPM control in your DAW and adjust to match the scale. (Reason DAW is already configured ion the template). BPM is the same for all 3 sequencers.

### Play / Stop
Play and stop all the 3 sequencers. It has 3 modes of operation, depending on the selected clock source:

- **INT** clock mode: PLAY/STOP play and stop de Reaktor rack. OSC mapped. 

- **EXT** CLock - **Ableton Link** : First you will need to midi map this controls to your DAW. Two play buttons are avalilable in this mode, one for Reaktor and one for Ableton. Reaktor can play or stop independent of Ableton, but is linked in beat, phase and tempo to the master clock of Ableton. Note: Ableton can start the playing in Reaktor if the sync option is selected in the midi output ports settings. In this mode Reaktor does not have a modular block to control the start/stop control inside the rack. Play/stop control works with a space bar message sent by the template, but it requires the "focus" on the Reaktor window to work. Unfortunately this is a limitation that you will need to take into account. A stream deck device is recommended to  easy the workflow. 

- **EXT** Clock - **Reason** (Or any other external DAW): First you will need to midi map this controls to your DAW. One play/stop button is available, that is mapped to your DAW. In this mode the DAW has the transport control, controlling the transport in Reaktor on sync. 

### Mute 
Mute the selected track (all 3 if LINK selected). The sequencer will continue running, but without MIDI output

### Reset
Reset the track position to the start on the selected track (all 3 if LINK selected). The start position is 1 or the last step, depending on the sequencer direction mode. 

### Pause
Pause the selected track (all 3 if LINK selected). The sequencer stops, with no MIDI output. Reaktor clock continue running. Once pause is disabled, sequencer will return playing on another step.   

### Step 
Advance one step the selected track (all 3 if LINK selected). This is useful to test your sequence.  


## Control

<div align="center"> 
<img src="images/img6.jpg" with=70% >
</div>

### Snapshots
The template supports a **snapshot** ( or preset) functionality, that allows you to save and recall up to four configuration values on each sequencer: note, gate, velocity and controls ( gate rate, shuffle, gate time, mode and steps). MIDI channel does not change with each snapshot. Each time you select a snapshot,  it automatically changes the value in the Reaktor rack. But be aware it is no bidirectional, that means, if you change a value in the Reaktor rack, it will not be updated to the template. The template acts as the "master" configuration. If you want to start from zero, just run press the CLEAR button with the LINK enabled to clear all values at once in the 3 sequencers and repeat it for each snapshot. 

### Link
LINK (L) button links the execution of commands, to execute it simultaneously on the 3 sequencers. The commands that works with "LINK" are: SNAPSHOT, CLEAR, NOTE, TRANSP, MUTE, RESET, PAUSE, and STEP. Just press the **L** button and the linked controls will change color to yellow. 

<div align="center"> 
<img src="images/img10.jpg" with=70% >
</div>

### Gate Rate
Select the gate rate of each track: 4th, 8th, 16th, 32th and 64th.

### Shuffle
Select a shuffle of each track to introduce variations in the rythm. (-50% to 50%). A diamond shaped button is provided to quickly return shuffle to 0%.

### Gate Time
Select a gate time of each track. (0 to 100)

### Mode
Select one of the 8 sequencer modes: FWD, REV, FWD-REV, TRI, PATT1, PATT2, RAND, GLITCH. 

- **FWD** (forward) = The sequence plays forwards.
- **REV** (reverse) = The sequence is reversed.
- **FWD-REV** (forward then reverse) = The sequence plays forwards and then backwards, for example: 1,2,3,4,4,3,2,1,1,2,3,4 etc.
- **TRI** (triangle) = Same as FWD-REV but adds an extra step at the end so that the first and last steps aren't repeated, for example: 1,2,3,4,5,4,3,2,1,2,3,4,5 etc.
- **PATT 1** (pattern 1) = Plays back the sequence using a pattern.
- **PATT 2** (pattern 2) = Plays back the sequence using a different pattern.
- **RAND** (random) = Plays back the steps randomly.
- **GLITCH** = Same as FWD except every so often plays a random step.

### Channel
Select the midi output channel for each sequencer track. Take care to use a midi channel that is not used by any other instrument and use a virtual MIDI port in your computer, that is not used or reserved by any other DAW or applications. On a PC you can use [loopMIDI](https://www.tobias-erichsen.de/software/loopmidi.html) to create virtual ports. On a Mac, you can use the IAC bus to create any number of virtual MIDI buses. This driver can be activated in the Audio MIDI Setup Utility.

### Steps
Select the number of up to 32 steps per sequencer track. The steps that are not used, change to a hidden state in the template, so you have a visual feedback of the steps available. 

<div align="center"> 
<img src="images/img11.jpg" with=70% >
</div>

### Clear
Initializes the values of the sequencer track (all 3 if LINK selected) to a starting values: 
- **GATE** = ALL SELECTED (1)
- **NOTE** = C3 (middle C)
- **VELOCITY** = 100
- **Gate Rate** = 4th
- **Shuffle = 0%
- **Gate Time = 50
- **MODE** = FWD
- **Steps** = 32 

Ocassionaly the template and reaktor rack files could be out of sync if you either does not save on sync the rack file and the template to keep the same values, or if you change the values directly in the reaktor rack. To return to a default configuration, just use the repository files, to start a new session from scratch. 


### Note display and zoom
Display the pitch values of each step on top of each step gate. Additionally a zoom button extend the note faders to easy input of notes. The convention used for numbering keys (notes) is where MIDDLE C (note #60) is C3. In piano scales the convention, Middle C is designated "C4". The "C3 Convention" is the most commonly used octave designation system on standard MIDI keyboards, most DAWs and Reaktor.  

<div align="center"> 
<img src="images/img12.jpg" with=70% >
</div>


### Transpose
The template has a -24 to + 24 interval keyboard to transpose the sequence (all 3 if LINK selected) without the need of an external midi controller. When you select transpose it displays the transpose keyboard on top of the velocity group. It also displays the transpose interval according to the key pressed, being C3 the central key. When you release transpose, the transpose keyboard returns to a hidden state. 

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
Select the value of the note on each step. It can be changed at any time and its value is stored automatically in the corresponding snapshot. But remember to mannualy save the template if you close it to keep the values. Depending on the number of steps selected, the note steps can be displayed or hidden. The note value that you change in the fader can be displayed when you press the Note button. If you press the zoom button, the note faders are expanded and you can more easily control the fader to setup a  note value. 

### Velocity section
Select the value of the velocity (volume level) on each step. Remember that the velocity signal will work only if your virtual or external instrument supports velocity control. It can be changed at any time and its value is stored automatically in the corresponding snapshot. But remember to mannualy save the template if you close it to keep the values. Depending on the number of steps selected, the velocity steps can be displayed or hidden. The velocity value that you change in the fader is displayed automatically in a pop up box over the note group. 


## MIDI setup



## OSC setup
