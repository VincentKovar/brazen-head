# Brazen Head: progress notes

Last updated: 2026-10-30.

## Files
- `brazen_head_oracle_v2.html`: desktop version (two tabs: Fortune Oracle, Voice & Automaton). Kept as is.
- `brazen_head_oracle_mobile.html`: the mobile version we are iterating on. This is the live one.
- `audio/new/`: the 12 recorded fortunes the page plays now (`fortune-01.m4a` to `fortune-12.m4a`, mono AAC 64 kbps, split from one GarageBand export `Brazen-fortunes.mp3`, levelled to about -17 dBFS). `audio/new/README.txt` has lengths and source times. The earlier organ-voice test recordings and their compact copies were removed from the working folder (still in the first commit, `8bf2bca`).
- `audio/README.txt`: older naming notes for the first set.
- Original draft (never edited): `~/Desktop/brazen_head_oracle (1).html`.

## What the mobile page does now
- Single phone-width column: title, 3D head, State Thy Query box, brass PULL lever, Hear Again / Save Audio / Share Card, settings accordion.
- The Head sleeps until knocked three times (click or tap the head). After a fortune, tapping the written fortune closes it and the Head sleeps again.
- Lever: drag or tap; knob slides right, slow return while the Head "thinks"; the Head only speaks once the knob is home. Pulling while asleep jams the lever.
- Fortunes: 12 entries in `FORTUNES` (text plus optional `audio` file). Shuffled deck, no repeats until all are used. Add more by hand.
- Voice order: recording (if the fortune has a file) -> chosen voice service (if a key is entered) -> browser voice.
- Voice service switch in settings: Gemini (writes answers and speaks) or ElevenLabs (voice only; model `eleven_turbo_v2_5`, five premade voices plus a custom voice ID). ElevenLabs confirmed working by the user. With ElevenLabs selected, fortunes come from the deck.
- Brass Voice switch (footer): low, rounded bronze timbre on recordings, Gemini and ElevenLabs audio (pitch down 12% for recordings, 10% for API voices). Hand-tuned settings: deep boost +4.5 dB, low-end boost +6.5 dB, chest +4 dB at 380 Hz, second voice 0.33, reverb loudness 0.19, echo tail 1.4 s. Does not affect the browser voice.
- Sound: ticking, bell, knocks, lever clunks, steam samples (embedded) plus synthesized hiss. Sound button mutes all effects.
- Steam from crown, shoulders and mouth. Steam levels confirmed balanced by the user.
- Voice & Automaton controls (message box, Animate & Speak, Download Audio, Silence) now live inside "Gemini Key & Voice Settings". The message box defaults to "Time is. Time was. Time is past."
- Share Card: fixed-size card preview with Download PNG.
- Messages stay on screen about 2.5 s plus 55 ms per character; tap to dismiss. A failed recording load now says so instead of silently using the browser voice.
- Save Audio follows the Brass Voice switch. After a performance it saves the whole thing as a stereo .wav (voice, bell, ticks, steam, lever clunks), recorded live with MediaRecorder. If the switch has changed since, or there was no performance, it saves the voice alone: rendered offline through the Brass chain when the switch is on, or the original file/audio when off. Browser voices cannot be saved.

## Open items
1. Listen to all 12 recordings against their texts (order was matched by position and clip length only).
2. Consolidate the query styles (Yea/Nay code is still in the script but switched off).
3. Test on a real iPhone: audio unlock, voice, lever drag.
4. Gemini voice, oracle text and audio download have never been tested with a real key (ElevenLabs has been).
5. Push the page and `audio/new/` to GitHub together (recordings load over the web, not from a local file; the right panel needs a local server such as `python3 -m http.server`).
6. Possible polish: fortune box covers the face a bit; knock prompt overlaps the base.
