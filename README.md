# Generative Music Playground

An interactive site where users can experiment with AI-generated music—choose a mood, genre, or instruments, and the app creates a unique song on the fly using the MusicGen model from Meta. The app uses prompt engineering to translate user preferences into natural language prompts for MusicGen, generating unique audio on demand.

## Features
- Select mood, genre (optional), and instruments
- Customize music parameters (tempo, length, key, scale, structure, intensity, energy, extra context)
- Generate unique music using AI (MusicGen-medium)
- Download generated audio files
- Robust backend and frontend input validation
- Timeout and error handling for model inference
- Modern web UI (Next.js + React)

## Tech Stack
- **Backend:** FastAPI (Python), MusicGen (via Hugging Face Transformers), Torch, soundfile
- **Frontend:** Next.js (React, TypeScript)
- **Environment:** Managed with [uv](https://github.com/astral-sh/uv)

## How it Works
- User selects mood, genre, instruments, and parameters in the UI
- The backend translates these into a structured prompt (e.g., "sad jazz piano music at 120 BPM in the key of C major")
- MusicGen-medium generates audio based on the prompt
- The app returns a downloadable audio file


## Testing
- Backend: `pytest tests/test_music_generation.py -v` (model is mocked for fast, reliable CI)
- Frontend: See `frontend/README.md` for details

## Project Status (2025-04-17)
- Prompt engineering and robust backend/frontend validation & testing completed
- Next up: Frontend user experience improvements (loading indicator, track history, error handling, mobile/responsive design)
- Future: Refine prompt engineering further, melody upload, user accounts, sharing, branding, deployment

## License
MIT License (see LICENSE file). **Generated content may not be used for commercial purposes.**

---

## Future Features
- **Melody-Guided Generation:** Support for MusicGen-melody, allowing users to upload or record a melody for the AI to build upon.
- **Improved audio realism:** MIDI-to-audio rendering, soundfont support, or advanced MusicGen models.
- **User accounts and history**
- **More advanced prompt engineering**
- **Frontend UX improvements**
