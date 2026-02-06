# AI Music Mastery System

A complete automated music production pipeline that takes a vocal recording and produces a fully mastered track.

## Features

- **Vocal Analysis**: Automatically detects pitch, tempo, key, and mood from vocal recordings.
- **Instrumental Generation**: Generates matching instrumentals using:
  - `synthetic`: Built-in synthesizer logic.
  - `mubert`: Mubert API integration.
  - `musicgen`: Local Meta MusicGen (via audiocraft).
- **Audio Alignment**: Time-stretches and loops instrumentals to match vocal timing.
- **Mastering Engine**: Professional mixing and mastering using `pedalboard` effects (compression, EQ, reverb) or basic fallback processing.

## Usage

```python
from ai_music_mastery import MusicMasterySystem

# Initialize
system = MusicMasterySystem(instrumental_service="synthetic")

# Process
metadata = system.process(
    vocal_path="vocals.wav", 
    genre="pop", 
    output_path="final_song.wav"
)
```

## Dependencies

- `librosa`
- `soundfile`
- `numpy`
- `pydub`
- `requests`
- `pyrubberband` (optional, for quality time-stretching)
- `pedalboard` (optional, for pro mastering)
