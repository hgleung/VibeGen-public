# Generative Music Playground

An interactive site where users can experiment with AI-generated music—choose a mood, genre, or instruments, and the app creates a unique song on the fly using the MusicGen model from Meta. The app uses prompt engineering to translate user preferences into natural language prompts for MusicGen, generating unique audio on demand.

## Features
- Select mood, genre (optional), and instruments
- Customize music parameters (tempo, length, key, scale, structure, intensity, energy, extra context)
- Generate unique music using AI (MusicGen-medium)
- **Audio playback with download link after generation**
- **Progress bar for estimated generation time**
- **API returns actual generation time in seconds**
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

## Usage

- **Backend:**
  - Run: `uvicorn app.main:app --reload`
  - API endpoint: `POST /api/music/generate` (see below for parameters)
- **Frontend:**
  - Run: `cd frontend && npm install && npm run dev`
  - Access at: `http://localhost:3000`
- **Tests:**
  - Backend: `pytest tests/test_music_generation.py -v` (model is mocked for fast, reliable CI)
  - Frontend: See `frontend/README.md` for details

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

## Project Status (2025-04-17)
- Prompt engineering and robust backend/frontend validation & testing completed
- **Generation time is now included in the API response.**
- **Audio download link appears after music is generated.**
- **Generated content is strictly non-commercial.**
- Next up: Frontend user experience improvements (loading indicator, track history, error handling, mobile/responsive design)
- Future: Refine prompt engineering further, melody upload, user accounts, sharing, branding, deployment

## License

- **MIT License** (see LICENSE file)
- **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)**
- **Generated content may not be used for commercial purposes.**
- **The model and weights used in this program are from Meta Platforms, Inc. and affiliates.**
- See LICENSE file for full terms, attributions, and additional non-commercial clause.

## Attribution & Disclaimer

- This project uses the MusicGen model and weights from Meta Platforms, Inc. and affiliates.
- All generated content is for personal, educational, or research use only.
- Commercial use, resale, or distribution of generated content is strictly prohibited.
- The software and generated content are provided "as is" with no warranty of fitness or merchantability.

## Limitations
- Model output quality may vary; not all prompts will yield musically pleasing results.
- Generation is slow for longer durations; max 10 seconds enforced for user experience.
- Non-commercial use only; see LICENSE for details.

## Future Features

### Radio & Continuous Music
- **Streaming Radio:** Continuous music generation with real-time parameter updates
  - Smooth transitions between different musical settings
  - Dynamic duration management for melodies/songs (30s to 3min)
  - Intermittent variation in musical patterns
  - Real-time mood/genre switching with crossfade
  - Custom transition timing settings
- **Promotional Streams:**
  - Permanent radio stream on main site with live listener count
  - YouTube lofi promotion channel integration
  - 24/7 automated streaming with genre rotation
  - Chat integration for live requests

### User Authentication & Security
- **Robust User Authentication:**
  - X (Twitter) integration for login
  - Automatic verification for X verified users (priority access)
  - Secure session management with JWT
  - 2FA option for enhanced security
  - Password-less login via X
- **Security Measures:**
  - Protected API endpoints with rate limiting
  - Database security with encryption at rest
  - User authentication with OAuth 2.0
  - Rate limiting:
    - 5 generations per hour for free users
    - 30 generations per day maximum
    - Verified users get higher limits
  - DDoS protection and WAF integration
  - Regular security audits
  - GDPR compliance for user data

### User Profiles & Storage
- **User Profiles:**
  - Personal track collection
  - Maximum 20 stored tracks per user (expandable for verified)
  - Permanent deletion option with 7-day grace period
  - Generation history and favorites
  - Custom profile pages
  - Achievement badges for generations
- **Database Integration:**
  - User data management in PostgreSQL
  - Track storage with AWS S3
  - Usage analytics and metrics
  - Backup and recovery systems
  - Caching layer for popular tracks

### Social Features
- **Track Sharing:**
  - Direct posting to site
  - One-click share to X
  - Share generation prompts
  - Embeddable player for external sites
  - QR codes for mobile sharing
- **Browse Tab:**
  - Social media-style feed with infinite scroll
  - View other users' generations
  - Tweet-length descriptions (280 chars)
  - Original prompts displayed
  - Community engagement (likes, reposts)
  - Trending section for popular tracks
  - Weekly featured artists
  - Genre-based browsing
  - Advanced search with filters

### Timeline
- **Phase 1 (Current):** Core generation features
- **Phase 2 (2 weeks):**
  - User auth with X integration
  - Basic profiles
  - Track storage (20 limit)
  - Simple sharing
  - Rate limiting

#### Detailed Phase 2 Implementation Schedule

**Week 1 (April 18-24, 2025)**
- Day 1: Database & Storage Setup
  - PostgreSQL setup
  - AWS S3 configuration
  - Schema design
- Day 2-3: Authentication
  - X OAuth implementation
  - JWT & session management
  - Protected routes
- Day 4-5: User Profiles
  - Track storage system
  - Profile UI/UX
  - Basic rate limiting
- Day 6-7: Sharing Features
  - Track sharing API
  - Public track views
  - X integration

**Week 2 (April 25-May 1, 2025)**
- Day 8-9: Security & Management
  - Rate limiting refinement
  - User dashboard
  - Usage tracking
- Day 10-11: Social Features
  - Public profiles
  - Search & filters
  - Track history
- Day 12: Mobile Updates
  - Responsive design
  - Touch interactions
  - PWA setup
- Day 13-14: Testing & Launch
  - Security testing
  - Performance optimization
  - Documentation
  - Deployment prep

**Critical Dependencies**
- Database before auth
- Auth before profiles
- Storage before tracks
- Profiles before sharing
- Rate limiting before launch

- **Phase 3 (Future):**
  - Radio features
  - Advanced social features
  - Enhanced security
  - Mobile app

### Technical Improvements
- **Melody-Guided Generation:** Support for MusicGen-melody, allowing users to upload or record a melody for the AI to build upon.
- **Improved audio realism:** MIDI-to-audio rendering, soundfont support, or advanced MusicGen models.
- **User accounts and history**
- **More advanced prompt engineering**
- **Frontend UX improvements**
