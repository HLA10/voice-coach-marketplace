# Voice Coach

A coaching plugin that helps learners improve their accent, their ear, and their daily speaking habits in **English (General American)**, **French (Parisian)** and **Swedish (Standard / Central Swedish)**.

## What it does

| Skill | Use it to |
|-------|-----------|
| `accent-coach` | Fix individual sounds, word stress, rhythm and intonation with step-by-step drills |
| `listening-trainer` | Train the ear: sound discrimination, dictation, shadowing, connected-speech decoding |
| `practice-planner` | Build a daily plan, run check-ins, and keep a simple progress log |

## How speech is checked

Claude cannot hear audio on its own. The plugin works in three ways:

1. **Typed or phonetic input**: the learner types what they said (or a respelling) and Claude diagnoses likely errors.
2. **Description**: the learner describes how a sound felt or how they think it sounded, and Claude coaches from that.
3. **Speko connector**: the plugin includes the [Speko](https://mcp.speko.ai/mcp) connector. It generates spoken model audio (`audio.synthesize`) and transcribes learner recordings (`audio.transcribe`) so Claude can compare what was said with the target. Learners connect and sign in to Speko when they install the plugin. Recordings must be shared as HTTPS links that download without a sign-in, and learners are asked before anything is sent to the service. The plugin still works without it, in text mode.

## Progress log

Learners keep a single file, `voice-coach-log.md`, in their working folder. The skills read it at the start of a session and update it at the end. See `skills/practice-planner/references/log-template.md`.

## Accent targets

One standard per language: General American English, Parisian French, Standard (Central) Swedish. The sound guides live in `skills/accent-coach/references/`.
