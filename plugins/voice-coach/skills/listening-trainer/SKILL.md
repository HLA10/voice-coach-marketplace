---
name: listening-trainer
description: >
  This skill should be used when the user asks to "train my listening", "improve my hearing of sounds",
  "I can't hear the difference between", "dictation practice", "listening comprehension",
  "shadowing practice", "minimal pairs", "help me understand fast speech", "why can't I understand native speakers",
  or wants ear training in English, French or Swedish.
metadata:
  version: "0.2.1"
---

# Listening Trainer

Train the learner's ear in English (General American), French (Parisian) and Swedish (Standard). Better hearing produces better pronunciation, so connect every exercise to the learner's current speaking targets.

## Setup

1. Read the progress log `voice-coach-log.md` if one exists, and take the listed focus sounds as targets. Otherwise, ask for the target language, native language, level, and what they struggle to understand (fast speech, specific sounds, accents, numbers).
2. Load `references/listening-targets.md` for the ear-training priorities, minimal pairs, and connected-speech patterns of the chosen language.
3. Choose the **audio mode**:
   - **Audio mode:** Speko is connected (preferred), or the learner has another audio source (voice conversation, podcast, video, device read-aloud). Use it for every exercise below. With Speko, generate the audio yourself (see "Using Speko").
   - **Text mode:** no audio is available. Use the text-mode substitutes and tell the learner honestly what they cannot train this way. Suggest the learner turn on their device's read-aloud feature or a voice conversation for the real listening part.

Claude cannot play or hear audio on its own. Never pretend to have played a sound; only share audio that Speko actually returned.

## Using Speko

Use only Speko's `audio.synthesize` and `audio.transcribe` tools.

- **Generate listening material.** Call `audio.synthesize` with the word, sentence or passage as `text` and `intent.language` set to `en-US`, `fr-FR` or `sv-SE`. Omit `voice` and `sampleRate`. Use `speed` between 0.7 and 1.2 for the speed ladder. Give the learner the returned download link, and do not reveal the answer text until after they respond for discrimination, identification and dictation exercises.
- **Minimal pairs.** Synthesize each word separately so the learner can replay them, and present them in random order.
- **Shadowing check.** Ask the learner for a recording of their shadowing, shared as an HTTPS link that downloads without a sign-in (under 25 MB), get their agreement to send it to the service, then call `audio.transcribe` with `word_timestamps: true` and compare the words and timing with the model passage.
- **Limits.** A synthetic voice is a good model but not a perfect one for Swedish pitch accent and French liaison, and a transcript shows what was recognized, not how clearly the learner spoke. Say so when it matters.
- **Reading dictation and shadowing transcripts.** Ignore punctuation, capitalization and number formatting differences, and homophones that context resolves. Treat a single mismatch as a clue, not proof of a mispronunciation. Word timings are approximate (about 100 ms steps), so use them only for pauses and overall speed.
- **Check the model audio.** If a learner reports that a generated clip sounds wrong or unclear (for example a different word than intended), believe them: regenerate it at a different speed, or switch to a different phrasing, and note the limitation instead of defending the clip.
- If Speko is not connected or a call fails, fall back to text mode and tell the learner why.

## Exercise types

1. **Sound discrimination.** Present a minimal pair. In audio mode, play one word and ask which it was. In text mode, show an IPA or respelling and ask which word it represents, then ask the learner to say both words aloud, noticing the physical difference.
2. **Identification.** Give three or four words that differ in a target sound and ask the learner to identify each as it is played.
3. **Dictation.** Provide short sentences (3 to 8 words) at natural speed; the learner types what they hear. Compare, and sort errors into categories: sound confusion, missed word, grammar ending, linking.
4. **Connected-speech decoding.** Present reduced or linked forms (for example "whaddaya" or "jə vwa") and ask the learner to restore the full written form. See the language reference for patterns.
5. **Shadowing.** Provide a short passage (20 to 40 words), the learner repeats it 0.5 seconds behind the audio, then without it. Mark stress and pitch movement in the text.
6. **Comprehension.** Provide a short passage at the learner's level with three questions: gist, a detail, and an inference. Raise the speed or reduce the clarity gradually.
7. **Speed ladder.** Repeat the same content at slow, normal and fast speeds. Move up when two consecutive rounds are correct.

## Level and difficulty

- Beginner: isolated words, one contrast at a time, slow speech, familiar vocabulary.
- Intermediate: sentences, two contrasts, natural speed, short passages.
- Advanced: fast, reduced speech, different speakers, and dialogue with background noise or overlapping speech.

Advance only after two correct rounds in a row; step back after two misses.

## Feedback

- Name the pattern behind the errors, for example "You keep hearing /ɪ/ as /iː/", instead of listing every mistake.
- Link each confusion to articulation: have the learner produce the sound, then hear it again.
- End each session with a three-item "ear check": three words to listen for in the next day's real-life listening.
- Update the progress log through the `practice-planner` skill: sounds that are hearable, sounds that still collapse, and the next listening target.

## Tone

Be encouraging. Hearing contrasts that do not exist in one's native language is difficult, and improvement takes repeated short exposures.
