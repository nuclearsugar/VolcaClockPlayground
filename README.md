#Volca Clock Playground

This Pure Data patch is a realtime clock augmentation tool for the Korg Volca series. By inputting the Volca clock into a computer, we can then play with the clock, and then send it into another Volca.

###Features
- Modules include: `clock divider`, `clock multiplier`, `multiplier pulse`, `swing`, `swing pulse`, `skip step`, `random pass thru`, `mute`, `internal metronome`, and `manual trigger`.
- The `Mute Line-in & Use Metro` will use an internal metronome instead of an external clock source. This is useful if you want to use this Pure Data patch as the master clock source. Or if you don’t have an audio interface.
- The `Multiplier Pulse` will automatically turn on and off the `Clock Multiplier` after a set number of beats. The same goes for the `Swing Pulse`.
- The `Metro Sound` is useful for listening to the clock source itself, especially since the clock pulse will damage your speakers. It will instead replace the clock pulse with a typical metronome sound. You can also select the metronome time signature by adjusting the `Metro Beats Per Bar` and therefore affect where the up beat lands.
- Two versions of this patch are available: GUI and editable. The GUI version (VCP_GUI.pd and VCP_GUI_core.pd) is optimized for performance and doesn't have clutter blocking your view. The editable version (VCP_Editble.pd) has a clear signal path and is much easier to edit; so you can edit the clock division rates or add your own module if desired.

###Requires use of Pd-Extended
http://puredata.info/downloads/pd-extended/releases/0.43.4

###Watch a demo
[![Volca Clock Playground Demo](https://img.youtube.com/vi/D63YXrjken0/0.jpg)](https://www.youtube.com/watch?v=D63YXrjken0)

###Example hardware setups
- **Using an external audio interface**
  - Volca Beats (sync out) > Audio interface input > Computer > Audio interface output > Volca Keys (sync in)
- **Using the built-in audio card of a computer**
  - Volca Beats (sync out) > Computer mic input > Computer audio output > Volca Keys (sync in)
- **No audio interface, instead use computer as master clock source**
  - Computer (headphones out) >>> Volca Keys (sync in)

###Getting Started
1. Open the patch within Pure Data: *VCP_GUI.pd*
2. Checkmark `Enable DSP`
  - This lets Pure Data process the incoming signal
3. Turn up `View Signal` and watch the VU meter
  - Check that the Volca clock is actually incoming correctly. You will probably need to adjust the Pure Data settings in top toolbar: Media/Audio Settings and check the input device and output device.
4. If needed, adjust the `Line-in Level`
  - If the input signal is too low then nothing will happen.
5. Check your system output level
  - If the output signal is too high then the receiving Volca will skip in a bizarre way. A good starting point is a volume of 50%.
6. If neeeded, tweak the `Latency Offset`
  - If Pure Data and your audio interface are introducing too much latency, then you might need to purposefully add extra latency. This will hopefully push the augmented clock to be only one step behind, which is tricky to land precisely. But I suggest you first just start playing and then “tune” this if necessary after seeing how it feels.
