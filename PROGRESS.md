# Brazen Head: progress notes

Last updated: 2026-10-23 (end of day).

## Files
- `brazen_head_oracle_v2.html`: desktop version (two tabs: Fortune Oracle, Voice & Automaton). Kept as is.
- `brazen_head_oracle_mobile.html`: the mobile version we are iterating on. This is the live one.
- `audio/`: recorded fortunes. `README.txt` lists the file name for each fortune text.
  - `fortune-01.mp3`, `fortune-02.mp3`: first two recordings (organ-style voice, stereo 128 kbps, about 20-24 s).
  - `audio/compact/*.m4a`: smaller mono 64 kbps copies of the same two (about 45% of the size). Not wired in yet.
- Original draft (never edited): `~/Desktop/brazen_head_oracle (1).html`.

## What the mobile page does now
- Single phone-width column: title, 3D head, State Thy Query box, brass PULL lever, Hear Again / Save Audio / Share Card, settings accordion.
- The Head sleeps until knocked three times (click or tap the head). After a fortune, tapping the written fortune closes it and the Head sleeps again.
- Lever: drag or tap; knob slides right, slow return while the Head "thinks"; the Head only speaks once the knob is home. Pulling while asleep jams the lever.
- Fortunes: 12 entries in `FORTUNES` (text plus optional `audio` file). Shuffled deck, no repeats until all are used. Add more by hand.
- Voice order: recording (if the fortune has a file) -> Gemini voice (if a key is entered) -> browser voice.
- Brass Voice switch (footer): bronze filtering, metallic ring and chamber echo on recordings and Gemini audio. Does not affect the browser voice.
- Sound: ticking, bell, knocks, lever clunks, steam samples (embedded) plus synthesized hiss. Sound button mutes all effects.
- Steam from crown, shoulders and mouth. Steam levels confirmed balanced by the user.
- Voice & Automaton controls (message box, Animate & Speak, Download Audio, Silence) now live inside "Gemini Key & Voice Settings". The message box defaults to "Time is. Time was. Time is past."
- Share Card: fixed-size card preview with Download PNG.

## Open items
1. Choose the best recorded voice for the main fortunes; record the other 10. Decide whether to use the compact `.m4a` copies (then change the `audio` names in `FORTUNES`).
2. Consolidate the query styles (Yea/Nay code is still in the script but switched off).
3. Test on a real iPhone: audio unlock, voice, lever drag.
4. Gemini voice, oracle text and audio download have never been tested with a real key.
5. Push `audio/` to GitHub next to the HTML (recordings load over the web, not from a local file).
6. Possible polish: fortune box covers the face a bit; knock prompt overlaps the base.
