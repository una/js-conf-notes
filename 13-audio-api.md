Building a musical instrument with the Web Audio API by [Steve Kinney](http://twitter.com/stevekinney)
---

- first create audio `context`
- `destination`: your amplifier -- what you're plugging everything into
- `const context = new AudioContext(); context.destination`
- then make `oscillator`
- oscillator creates a sound wave -- sound is a vibration in the air
- amplitude = how high the beats are and how loud
- `oscillator.start(0)` = start immediately
- create gain node, then hook up oscillator to gain node -- gives illusion of turning oscillator off and on
- set frequency value with `oscillator.frequency.value = 220` --> `440` is default
- `sin`, `square`, `sawtooth`, `triangle` == default oscillator waves --> [demo here](http://stevekinney.github.io/toney-danza/)

> "Disconnect your oscillators when you're done. It's the responsible thing to do."

- set notes to frequencies --> use math to match notes. *(works only in one key, AKA harmonica)*
- [Octavian](https://github.com/stevekinney/octavian)

> "When you have a little code, a good idea, and a cute name, you have the beginnings of an open-source project"

- [Demo Time!](http://stevekinney.github.io/audiophonic/)

- Synthesizers in our web browsers mean *web browsers in our synthesizers!*
- Face Theramin -- awesome [demo](http://stevekinney.github.io/face-theremin/) that detects your face and creates pitch based on distance from camera
- Make music sequences [demo](http://socket-synth.herokuapp.com/) --> could have lots of people making music together
- can *build* musical instruments because hardware! **Music Bots :sound:**