#Volca Clock Playground

This Pure Data patch is a realtime clock augmentation tool for the Korg Volca series. By inputting the Volca clock into a computer, we can then play with the clock, and then send it into another Volca.

###Features
- Modules include: `clock divider`, `clock multiplier`, `multiplier pulse`, `swing`, `swing pulse`, `skip step`, `random pass thru`, `mute`, `internal metronome`, and `manual trigger`.
- The `Mute Line-in & Use Metro` will use an internal metronome instead of an external clock source. This is useful if you want to use this Pure Data patch as the master clock source. Or if you don’t have an audio interface.
- The `Multiplier Pulse` will automatically turn on and off the `Clock Multiplier` after a set number of beats. The same goes for the `Swing Pulse`.
- The `Metro Sound` is useful for listening to the clock source itself, especially since the clock pulse will damage your speakers. It will instead replace the clock pulse with a typical metronome sound. You can also select the metronome time signature by adjusting the `Metro Beats Per Bar` and therefore affect where the up beat lands.
- Two versions of this patch are available. The GUI version *(VCP_GUI.pd and VCP_GUI_core.pd)* is optimized for playing and doesn't have clutter blocking your view. The editable version *(VCP_Editble.pd)* has a understandable signal path and is easier to edit; so you can edit the settings or add your own module if desired.

###Requires use of Pd-Extended
It's free and open source. Available for Mac, Windows, & Linux.<br>
http://puredata.info/downloads/pd-extended/releases/0.43.4

###Watch a demo of VCP in action
[![Volca Clock Playground Demo](https://img.youtube.com/vi/D63YXrjken0/0.jpg)](https://www.youtube.com/watch?v=D63YXrjken0)

###Example hardware setups
- Using an external audio interface
  - *Volca Beats (sync out) > Audio input > Computer > Audio output > Volca Keys (sync in)*
- Using the built-in audio card of a computer
  - *Volca Beats (sync out) > Computer mic input > Computer audio output > Volca Keys (sync in)*
- No audio interface, instead use computer as master clock source
  - *Computer (headphones out) > Volca Keys (sync in)*

###Getting Started
1. Open the file *VCP_GUI.pd* within Pure Data.
2. Checkmark `Enable DSP`.
  - Without this checkmarked, no input or output audio is possible!
3. It's imporant to confirm that the *input device* and *output device* is correct.
  - The settings panel can be found in the top toolbar: *Media > Audio Settings*
4. If you have a line-in signal, turn up `View Signal` and make sure the the VU meter is moving.
  - This is just to confirm that the Volca clock is actually being received within Pure Data. If you don't see the VU meter moving at all, then your settings probably are not setup correctly either in Pure Data, audio interface, or system settings. 
  - If you can see the VU meter moving and yet the yellow box for `Input Clock` isn't flashing to the beat, then the input signal is too quiet and you should increase the `Line-in Level`.
5. Check your system output level.
  - If the output signal is too high then the receiving Volca will skip in a bizarre way. A good starting point is a volume of 50%.
6. If neeeded, tweak the `Latency Offset`.
  - If Pure Data and your audio interface are introducing too much latency, then you might need to purposefully add extra latency. This will hopefully push the augmented clock to be only one step behind, which is tricky to land precisely. But I suggest you first just start playing and then “tune” this if necessary after seeing how it feels.

###Watch a demo - Snap your fingers to drive the Volcas
Stumbled across a happy accident when creating this tool.  I realized that I could use a person to drive the tempo of the Volcas. This can be as simple as your hands clapping and using the built-in mic of a Mac laptop. Or it can be more complex and mic only the kick drum of an actual drummer. Lots of possibilities to explore!
[![Snap your fingers](https://img.youtube.com/vi/7tdasezAuxI/0.jpg)](https://www.youtube.com/watch?v=7tdasezAuxI)
