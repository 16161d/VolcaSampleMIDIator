# VolcaSampleMIDIiator

Built with Cycling 74's Max 8 software.

This simple app aims to emulate some of the features that the RetroKits RK-002 Smart MIDI cable w/ Volca Sample firmware does.

Instructions !

Select your master or controlling MIDI device from the drop down menu. 

Select the MIDI device connected to your Volca sample. The following effects should now be in place:

[Velocity Sensitivity]

The Volca Sample will now respond to velocity control data.

['Single' Channel Control]

The sample control base key sets the root note from where you can trigger each individual sample currently set accross the Volca Samples active 10 MIDI channels.

eg. C2 = Note C2 (Sample 1), Note C2# (Sample 2) etc.

[Chromatic Control]

The chromatic control is current set with a range of -/+ 12 semitones. Due to how this MIDI hack works, the samples won't be perfectly pitched in tune, the same is true for the RK-002.

Setting the sample control base key will automatically shift the chromatic base note two octaves higher

eg. Sample control base key of C2 sets the Chromatic base key to C4.


Notes on limitations !
Because of the limitations in the design of the Volca Sample by KORG when implementing midi*, this app doesn't "add" any new features, but simply intercepts and reroutes MIDI data to controls that do provide the closest functionality. MIDI note data instead sends Pitch control change messages to the active MIDI channel accross the set range, velocity data is instead sent to Level CC for the active MIDI channel. 

I don't think this app fully recreates all of the features of RetroKits RK-002, but I aimed to recreate the most sought after ones. I still recommend the RK-002 as it can be loaded with all other kinds of custom firmware and is better suited to hardware only or live setups. I will never be recording or playing with things being connected to my computer, so I can live with this alternative.

* This is not so much a criticsm or a comment that the design is bad, it makes perfect sense for what the Volca Sample is, but there will always be a small percentage of people who want to use something in a way that it wasn't intended for :)



