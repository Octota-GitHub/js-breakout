# js-breakout
JavaScript Breakout

Based on:

* the [MDN Pure Javascript Breakout Tutorial](https://developer.mozilla.org/en-US/docs/Games/Tutorials/2D_Breakout_game_pure_JavaScript)
* the [tones.js](https://github.com/bit101/tones) WebAudio sample due to [Keith Peters](https://github.com/bit101)

This is primarily a vehicle for my experimentation, learning some practical Javascript and HTML. The end result of the MDN tutorial was far too tempting to leave alone, especially in quarantine.

In the near term I hope to move the animation model to a time-based system that isn't reliant on an assumed frame rate with one tick per frame. That will make it possible to stand up an animation model that is also time-based for things like flash effects and other events.

Game features in no particular order:

* three levels
* extra life at the end of level 2
* per level
    * ball speedup and rising speed limits
    * brick column/row increase
    * level 2 and above with shaded, variable brick shields (currently level-1 shields/brick)
* paddle zoned into slowdown/speedup areas, with audio hints on hit
* note-looping brick hit audio effects
* musical embellishment for ball miss, level complete, game over and game won (finishing level 3)

Tones.js has been enhanced in the direction of fully embedding the note/octave/attack/release specification in a single string argument. The bounceTone class' playSequence in breakout.html (and rendition of Ode to Joy) shows how this works to allow scoring simple music in note lists. Perhaps a "score" array should be pre-compiled into native objects but for now string parsing is effective. A notation that is more musically native could also be useful.

Tones also now supports querying out a given note frequency so that algorithimic musical generation can be implemented a bit more abstractly - the note-looping uses this to get the base frequency, which it bounceTone then loops on the even-tempered 12-note octave scale.