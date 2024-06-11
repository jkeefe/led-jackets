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

- Chase
- Pulse
- Starry
- Wavey / Alternating
- Slow
- Fast
- Lightning

### Special

- Music (Bass, with accelerometer)
- Dancing / Walking (using accelerometer)
- Sound (with microphone)

### Buttons

- Color (cycle through options, solids then rainbows, pastels, etc.)
- Vibe (cycle through patterns)
- Special (music, dancing, sound)
- Brightness (use logic from pendant?)
- Sync (with other Jacket)


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

------
## Using WLED

Exploring the possibility of using WLED to sync the jackets and have pretty patterns!

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



