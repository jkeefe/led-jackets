# Process Notes for LED-Jackets

This is where I keep my notes as I work along the way. Could include dead ends and bad ideas. Proceed with care.

## General Operation / Pseudocode

### Colors

- Reds
- Blues
- Purples
- Rainbows
- Sparkles
- Whites
- Pastels
- Confetti

### Patterns

- Solid
- Wavey / Alternating
- Chase
- Pulse Slow
- Pulse Fast
- Starry 
- Rows

### Special

- Music (Bass, with accelerometer)
- Dancing / Walking (using accelerometer)
- Sound (with microphone)
- Lightning

### Buttons

- Color (cycle through options, solids then rainbows, pastels, etc.)
- Vibe (cycle through patterns)
- Special (music, dancing, sound)
- Brightness (use logic from pendant?)
- Sync (with other Jacket)

Or ...

- Color & Pattern
- Special
- Brightness
- Sync

Or ...

- Color
    - Short: Pick a color or rainbow
    - Long: Cycle
- Pattern
    - Short: Pick
    - Long: Cycle
- Special
    - Short: Pick


## Sync

Both jackets have sync buttons

When pressed and held on both jackets:

- Nora's jacket becomes the "Central" ... looking for a Peripheral
- Nick's jacket becomes the "Peripheral" ... broadcasting a service (UART)

The connection process is indicated by blue lights doing connecty things on the jacket

Once connected:

- Nora's jacket transmits RGB code, using the adafruit color packet, but the "color" is really three values representing the jacket's _color mode_, pattern and special status.
- Initially the jackets are both some kind of connected blue pattern
- Then it switches to Nora's previous status
- Nick's jacket changes color mode, pattern and special to match.
- Changes in status on Nora's jacket instantly trigger changes in Nick's jacket

Press-and-hold again to disconnect


Likely use [this code](https://learn.adafruit.com/color-remote-with-circuit-playground-bluefruit/code-the-color-remote-with-circuitpython)

## Music Mode

Since we'd like this for dancing to music ... and reactive to the beat ... what if we looked for the low-freqency vibrations in the _acceleromenter_ instead of the microphone?

Here's an [example](https://robotsandphysicalcomputing.blogspot.com/2018/10/adafruit-circuit-playground-reacting-to.html).

<<<<<<< HEAD
Effect is either rows or full-jacket pulse/color

## Data structure

Each jacket will have a slightly different layout. 

Left-right pixels probably aren't close enough to have a good lateral effect. Also maybe too complicated. But up/down should work well, with rows. That said, I think the "sequence" of LED's should go all the way across the front of the jacket, from bottom to top, and then down the back of the jacket.

Skip any LEDs we don't want to light because they were just in transition from, say, back to front.

`SEQUENCE` = Array of LED ids from front bottom left to front bottom right, up one row across to left, etc ... then down the back the same way.

`ROWS` = Array of arrays. Each sub-array has contains all LED ids for an entire row around the jacket. The rows are ordered from bottom of jacket to top.
=======
------
## Using WLED
>>>>>>> 4e9c87850fe614168fef76628d8288a204260785

Exploring the possibility of using WLED to sync the jackets and have pretty patterns!

### Flashing

Use [this site](https://install.wled.me/).

### Controlling

It's [here](http://10.0.1.19/).

### Buttons

1. Cycle through non-music preset patterns (Long-press to toggle off and on)
2. Cycle through music-driven patterns
3. Cycle brightness down (then back to bright)

### Sync

- Set to sync patterns and colors, but not brightness. Both jackets, both ways.
- Be sure to toggle on the send synch option

### Matrix

- Set up the strip to be a matrix, with the front wrapping to the back

### Flash with audio responsiveness

Get those little microphones

## Wiring

- [Pinout](https://wiki.seeedstudio.com/XIAO_ESP32C3_Getting_Started/)
- [Battery](https://wiki.seeedstudio.com/XIAO_ESP32C3_Getting_Started/#battery-usage)
- [LEDs](https://kno.wled.ge/basics/getting-started/)
- [Level shifter](https://learn.sparkfun.com/tutorials/bi-directional-logic-level-converter-hookup-guide)
- [Buttons](https://kno.wled.ge/features/macros/)
- [Microphone](https://kno.wled.ge/advanced/audio-reactive/)


