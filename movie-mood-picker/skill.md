---
name: movie-mood-picker
description: >
  This skill should be used when the user wants movie recommendations based on their current
  mood, emotional state, or what kind of experience they want. Asks a short series of questions
  to understand the user's mood and context, then recommends 3–5 fitting movies or series with
  a brief rationale for each. Works for any genre, era, or platform.
user_invocable: true
compatibility:
  platforms:
    - claude-code
metadata:
  version: "1.1.0"
---

# Movie Mood Picker

Recommend the most fitting films or series based on how the user feels right now.

## Workflow

1. **Capture the mood** — Ask the user one open question: *"How are you feeling right now, or what kind of experience are you after tonight?"* Accept any answer — emotions ("tired and sad"), energy states ("low energy, just want to chill"), desires ("something thrilling"), or anti-preferences ("nothing too heavy").

2. **Ask 1–3 clarifying questions** — Based on the answer, ask only the questions that are genuinely unclear. Never ask all of them. Stop as soon as you have enough to make good picks.

   Choose from:
   - *"Are you watching alone or with someone?"* (see social context rules below)
   - *"Any genres, topics, or themes you want to avoid tonight?"*
   - *"Do you prefer something new to you, or are you open to revisiting something you've seen before?"*
   - *"Are you up for a full film, or would a short series or single-episode documentary also work?"*
   - *"How much time do you have — under 90 minutes, up to 2 hours, or no limit?"*
   - *"Do you want something easy to follow, or can you handle complexity (unreliable narrators, non-linear timelines, many characters)?"*

3. **Map mood to film attributes** — Internally translate the mood into concrete attributes before selecting:
   - Emotional tone (e.g., warm, dark, funny, tense, melancholic, uplifting)
   - Pacing (slow burn vs. fast-moving)
   - Complexity (straightforward arc vs. unreliable narrator / non-linear / ensemble)
   - Social context (see rules below)
   - Format (film, docuseries, single documentary episode)
   - Runtime constraint (if stated)
   - Rewatch vs. new (if stated)

   **Social context rules:**
   - Alone → can handle ambiguous endings, slower pacing, more challenging subject matter
   - With someone → needs a clearer arc, shared emotional payoff, avoids content that requires prior explanation

4. **Select 3–5 recommendations** — Choose films or series that genuinely fit the mapped attributes. Prioritise:
   - Fit to mood over popularity or critical acclaim
   - Range: at least one well-known pick and one less obvious pick
   - Variety in era if no preference was stated (not all from the same decade)
   - If rewatch is welcome, include one strong rewatch candidate clearly labelled
   - Respect the runtime constraint if one was given — do not recommend a 3-hour film to someone with 90 minutes

5. **Track what has been recommended** — Keep a running internal list of every title recommended in this conversation. Never recommend the same title again. If the user asks to refine and better options are running low, say so rather than recycling.

6. **Present recommendations** — For each film or series, provide:
   - **Title** (Year) — Director / Creator
   - **Format & runtime:** e.g., "Film · 96 min" or "Docuseries · 4 × 45 min"
   - **Why it fits your mood:** One sentence connecting the film's specific qualities to what the user said they wanted
   - **What to expect:** 2–3 sentences covering tone, pacing, and what makes it worth watching — no plot spoilers
   - **Best watched when:** One-line context (e.g., "late night alone", "with someone who likes dark comedy")
   - **Rewatch?** — Only include this line if it is a rewatch candidate: *"Worth revisiting — [one-line reason why it rewards a second watch]"*

7. **Offer to refine** — After presenting the picks, ask:
   - *"Have you seen any of these?"* — Replace seen titles immediately with fresh picks.
   - *"Want me to adjust — more of something, less of something, or a completely different direction?"* — Re-run from step 3 with the new input.

## Output Format

Present recommendations as a clean numbered list. Example structure:

---

**Your mood:** [one-line summary of what you heard]

**1. Movie Title (Year)**
*Director: Name*
**Format & runtime:** Film · 112 min
**Why it fits:** ...
**What to expect:** ...
**Best watched when:** ...

---

## Guidelines

- Never recommend a film just because it is famous — fit to mood is the only criterion that matters
- If the user's mood is ambiguous or contradictory (e.g., "happy but also want to cry"), lean into the tension — films that hold both tones often feel most satisfying
- For low-energy or comfort moods, favour warmth, familiarity, and a clear emotional arc over challenge
- For high-energy or restless moods, favour momentum, stakes, and strong forward drive
- Always include at least one film that is not the first thing that would come to mind — this is what makes the recommendation feel considered rather than generic
- If the user mentions a specific streaming platform, prioritise films likely available there — but do not make availability guarantees; direct them to JustWatch to verify
- Keep rationale language specific and grounded — avoid vague praise like "a cinematic masterpiece" or "visually stunning"
- Never recommend a title already shown in this conversation
