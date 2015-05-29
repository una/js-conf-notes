Recreating a dialup modem in javascript by [Sam Saccone](http://twitter.com/samccone)
---

- sound is just vibrations in the air
- data is just 0's and 1's

> language == the data encoding for speech

- "The noise I'm making means nothing if you don't know the language"

### History Time

- **1820(?)**: Optical telegraphy (bell sounding)
- **1836**: Morse code -- electrical signals over a wire.
- **1874**: 5-bit code for letters, Baudot
- **1855**: Multiplex information, up to 240 Baud
- **1876-**: Alex Bel, harmonic/audible telegraphy

- AFSK (Audible Frequency Shifting Key)
- 10 Baud modem sounds super high pitched -- can hear the 0's and 1's coding scheme
- teletype machine demo -- sends signals with sound, 45.45 baud (*we can send info over a phone line!*)
- **1942**: modem takes data, shifts, unshifts

### Recreating a Modem with JS

- Shift of frequency over time. [Live](http://samccone.github.io/noise/component-demos/oscillator.html)
- Bits --> audio
- The hard part: Data Extraction
- **Goertzel**: allows us to extract a single target frequency of intensity/time (dots above freq curve)
- need to also account for noise

**tl;dr: [Demo](https://github.com/samccone/noise)**