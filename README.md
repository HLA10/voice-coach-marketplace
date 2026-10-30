# Voice Coach Marketplace

A marketplace for **Voice Coach**, a plugin that coaches accent, pronunciation, rhythm and listening in English (General American), French (Parisian) and Swedish (Standard).

## Install

**Claude Cowork (desktop app)**
1. Open **Customize**, then **Plugins**.
2. Choose **Add marketplace** and enter `HLA10/voice-coach-marketplace`.
3. Install **voice-coach** from the list.
4. When asked, sign in to the Speko connector. It provides spoken model audio and recording transcription. Voice Coach also works without it, in text mode.

**Claude Code**
```
/plugin marketplace add HLA10/voice-coach-marketplace
/plugin install voice-coach@voice-coach-marketplace
```

## What you get

- **Accent coach**: sound, stress, rhythm and intonation drills.
- **Listening trainer**: discrimination, dictation, shadowing and connected-speech practice.
- **Practice planner**: daily plans and a progress log (`voice-coach-log.md`) that you keep.

See `plugins/voice-coach/README.md` for details and limits. Claude cannot hear audio itself, and transcripts show what was recognized, not how clearly you spoke.
