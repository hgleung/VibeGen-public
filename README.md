# Generative Music Playground

An interactive site where users can experiment with AI-generated music—choose a mood, genre, or instruments, and the app creates a unique song on the fly using the MusicGen model from Meta. The app uses prompt engineering to translate user preferences into natural language prompts for MusicGen, generating unique audio on demand.

## Features
- Select mood, genre (optional), and instruments
- Customize music parameters (tempo, length, etc.)
- Generate unique music using AI (MusicGen-medium)
- Download generated audio files
- Modern web UI (Next.js + React)

## Tech Stack
- **Backend:** FastAPI (Python), MusicGen (via Hugging Face Transformers), Torch, soundfile
- **Frontend:** Next.js (React, TypeScript)
- **Environment:** Managed with [uv](https://github.com/astral-sh/uv)

## How it Works
- User selects mood, genre, instruments, and parameters in the UI
- The backend translates these into a prompt (e.g., "sad jazz piano music")
- MusicGen-medium generates audio based on the prompt
- The app returns a downloadable audio file

## Getting Started

### Backend
1. Create and activate the Python virtual environment:
   ```bash
   uv venv
   source .venv/bin/activate
   ```
2. Install dependencies:
   ```bash
   uv pip install -r requirements.txt
   ```
3. Run the FastAPI server:
   ```bash
   uvicorn app.main:app --reload
   ```

### Frontend
1. Navigate to the frontend directory:
   ```bash
   cd frontend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the development server:
   ```bash
   npm run dev
   ```

## License
MIT License (see LICENSE file). **Generated content may not be used for commercial purposes.**

---

## Future Features
- **Melody-Guided Generation:** Support for MusicGen-melody, allowing users to upload or record a melody for the AI to build upon.
- **Improved audio realism:** MIDI-to-audio rendering, soundfont support, or advanced MusicGen models.
- **User accounts and history**
- **More advanced prompt engineering**
