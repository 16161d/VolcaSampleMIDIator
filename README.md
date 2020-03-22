# Volca Sample MIDIator

![midiator](/img/midiator.png)

This simple app aims to emulate some of the features that the [RetroKits RK-002 Smart MIDI cable](https://www.retrokits.com/rk-002/) w/ Volca Sample firmware does.

Built with Cycling 74's [Max 8 software](https://cycling74.com). The zip contains an OSX .app file, as well as a Max collective and Max patcher file. Please feel free to modify and do with the Max patch what you want, I'd appreciate any feedback from Max gurus on anything I can do to optimise the patch and make better use of existing objects.


## Instructions

Select your master or controlling MIDI device from the **MIDI IN** drop down menu. 

Select the MIDI device your Volca sample is connect to from the **MIDI OUT** drop down menu. 

The following effects should now be active:

### Velocity Sensitivity

The Volca Sample will now respond to velocity control data.

### 'Single' Channel Control

The **SAMPLE BASE KEY** sets the root note from where you can trigger each individual sample currently set accross the Volca Samples active 10 MIDI channels. This let's you play all 10 individual samples from your keyboard or sequence from one MIDI channel, using note data to change the active sample.

eg. C2 = Note C2 (Sample 1), Note C2# (Sample 2) etc.

### Chromatic Control

The chromatic control is currently set with a range of -/+ 12 semitones. Setting the **SAMPLE BASE KEY** will automatically shift the **CHROMATIC BASE KEY** two octaves higher.

eg. SAMPLE BASE KEY C1 = CHROMATIC BASE KEY C3, with C2 acting as your lower range.

Due to how this MIDI hack works, the samples won't be perfectly pitched in tune, the same is true for the RK-002 from what I hear (although their maths is probably more accurate than mine).

### MIDI Mapping

Here i've expanded a bit from the RK-002 by offering more control options. I've not included LEVEL as a mod destination because it will likely break or make weird things happen with velocity control. I've included aftertouch as a mod source, as well as 2 **CUSTOM CC #**.

Use the number boxes to the right of the **CUSTOM CC #** to set your CC source, such as the CC number output by your controllers pots or faders.

This feature is a little bit janky, and I may need to iron it out a bit more in the future, but it works. 

## Notes
Because of the limitations in the design of the Volca Sample*, this app doesn't "add" any new features, but intercepts and reroutes MIDI data to the controls that provide the closest functionality. MIDI pitch / note data instead sends Pitch control change messages to the active MIDI channel accross the set range, velocity data is instead sent to Level CC for the active MIDI channel. 

I don't think this app fully recreates all of the features of RetroKits RK-002, but I aimed to recreate the most sought after ones. I still recommend the RK-002 as it can be loaded with all other kinds of custom firmware and is better suited to hardware only or live setups, and should generally be more reliable than software. I rarely record or play my gear without it being connected to my computer, usually running through various other Max patches I've made, so I can live with this alternative.

\* This is not a criticism that the design is bad, it makes perfect sense for what the Volca Sample is, but there will always be a small percentage of people who want to use something in a way that it wasn't intended for :)

## Changelog

* **v2.0.0** - This more complete version comes with a new more appropriate look, adds the MIDI mapping feature, and fixes an issues with chromatic mode not pitching notes correctly.

* v1.0.1 - Fixed app not detecting hotswapped MIDI devices. Lists will now update and refresh if a MIDI device is connected or disconnected.

* v1.0.0 - First public version, may be issues, but has been tested thoroughly. An update may be made to include MIDI mapping.




