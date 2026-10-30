---
name: practice-planner
description: >
  This skill should be used when the user asks to "make me a practice plan", "daily practice routine",
  "track my progress", "voice coach check-in", "weekly review", "start voice coaching",
  "what should I practice today", "set my goals for accent training", or wants a schedule, goals,
  or a progress log for pronunciation and listening practice in English, French or Swedish.
metadata:
  version: "0.2.0"
---

# Practice Planner

Build a realistic daily routine, run check-ins, and maintain the learner's progress log. This skill ties together `accent-coach` and `listening-trainer`.

## Intake (first session)

Ask only what the log does not already answer:

1. Target language: English, French or Swedish (or more than one).
2. Native language(s).
3. Level: beginner, intermediate, advanced.
4. Goal: everyday clarity, work or study, a specific test or event, or sounding more natural.
5. Time available per day: 10, 20 or 30 minutes.
6. Hardest sounds, situations, or people to understand.
7. Whether the learner has audio available (voice conversation, device read-aloud, recordings) and whether the Speko connector is connected (it provides model audio and recording checks).

Summarize the answers in two lines and confirm before building the plan.

## Building the plan

Create a plan sized to the available time. Use this structure:

| Block | 10 min | 20 min | 30 min |
|-------|--------|--------|--------|
| Warm-up: breathing, jaw and lip loosening, one tongue-twister | 1 | 2 | 3 |
| Focus sound drill (`accent-coach`) | 4 | 7 | 10 |
| Listening exercise (`listening-trainer`) | 3 | 5 | 8 |
| Rhythm and intonation or shadowing | 2 | 4 | 5 |
| Speaking application: a 2-sentence answer or a short voice message | 0 | 2 | 4 |

Plan by week, not only by day:

- **Weeks 1 to 2:** one or two focus sounds, with matching listening contrasts.
- **Weeks 3 to 4:** add word stress, rhythm and intonation.
- **Weeks 5 to 6:** connect the sounds in sentences, then free speech and fast listening.
- **Every 7th session:** weekly review using the log (see below).

Rotate focus targets when a target reaches "mostly" status. Keep no more than two active at once.

## The progress log

The learner keeps a single file named `voice-coach-log.md`. Use the template in `references/log-template.md`.

- At the start of a session, look for the file in the working folder. If it exists, read it. If not, offer to create it.
- If file access is not available, give the learner an updated log block to copy and save, and ask them to paste it at the next session.
- At the end of a session, append a dated entry: focus targets, what was practiced, self-rated clarity (1 to 5), listening result, and tomorrow's 3-minute task. Update the status table.
- Never overwrite earlier entries. Keep the file short: summarize entries older than four weeks into a few lines.

Status values for each target: `not started`, `working`, `mostly`, `automatic`.

## Weekly review

After about seven sessions, or on request:

1. Compare the status table with the previous week.
2. Report three things: what improved, what is stuck, what to change.
3. Suggest an adjustment: slower or faster ladder, new focus, different listening material.
4. Celebrate concrete wins, such as a contrast that is now reliably heard.

## Tone

Be supportive and realistic. Small daily practice beats long occasional sessions. Never promise that accent change will be quick or complete.
