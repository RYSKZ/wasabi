## wasabi
A WASAPI audio stream renderer integrated with a WAV format specification checker and data reader.

---

#### Compatibility
For now, it only works with LPCM encoded WAV audio files that have the same parameters as the ones specified by the format of the default audio output device (you can check them in the Sound Control Panel, mmsys.cpl -> audio endpoint properties -> advanced options). In the future, the default format will be checked and the audio will be converted accordingly.

#### TODO:
- Implement WAVReader class constructor (rather than relying on default initialization) and destructor.
- Add parameter validation.
- Extend playback control by adding the possibility to skip forward and backward.
- Register a callback to receive notifications when the volume of the audio session has been changed using the Volume Mixer so that it is correctly updated when displayed on screen.
- Convert the audio to the same format that the default audio output device is using.
- Support more audio formats (such as other PCM types and non PCM encoded WAV files, FLAC, ALAC, AIFF, MP3, etc).
- DONE:
  - Load the audio in chunks from a separate thread rather than doing it all at once, thus decreasing the wait time until the playback begins and considerably reducing the memory footprint.
  - Add audio session volume control.
  - Add audio playback control.