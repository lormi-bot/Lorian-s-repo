---
name: movie-mood-picker
description: >
  This skill should be used when the user wants movie recommendations based on their current
  mood, emotional state, or what kind of experience they want. Asks a short series of questions
  to understand the user's mood and context, then recommends 3–5 fitting movies with a brief
  rationale for each. Works for any genre, era, or platform.
user_invocable: true
compatibility:
  platforms:
    - claude-code
metadata:
  version: "1.0.0"
---

# Movie Mood Picker

Recommend the most fitting movies based on how the user feels right now.

## Workflow

1. **Capture the mood** — Ask the user one open question: *"How are you feeling right now, or what kind of experience are you after tonight?"* Accept any answer — emotions ("tired and sad"), energy states ("low energy, just want to chill"), desires ("something thrilling"), or anti-preferences ("nothing too heavy").

2. **Ask 1–2 clarifying questions** — Based on the answer, ask only the questions that are genuinely unclear. Choose from:
   - *"Are you watching alone or with someone?"* (affects tone and content)
   - *"Any genres or topics you want to avoid tonight?"* (filters out wrong picks)
   - *"Do you prefer something new or are you open to classics?"* (era preference)
   - *"How much mental energy do you have — do you want something easy to follow or can you handle complexity?"*

   Never ask all four. Stop at two questions max if the mood is already clear enough.

3. **Map mood to movie attributes** — Internally translate the mood into film attributes before searching:
   - Emotional tone (e.g., warm, dark, funny, tense, melancholic, uplifting)
   - Pacing (slow burn vs. fast-moving)
   - Cognitive load (easy-watching vs. complex plot)
   - Social context (solo vs. group, date night vs. family)
   - Genre signals (if any)

4. **Select 3–5 movies** — Choose films that genuinely fit the mapped attributes. Prioritise:
   - Fit to mood over popularity or critical acclaim
   - Range: include at least one well-known pick and one less obvious pick
   - Variety in era if no preference was stated (not all from the same decade)
   - Avoid recommending the same film twice in the same conversation

5. **Present recommendations** — For each film, provide:
   - **Title** (Year) — Director
   - **Why it fits your mood:** One sentence connecting the film's specific qualities to what the user said they wanted
   - **What to expect:** 2–3 sentences covering tone, pacing, and what makes it worth watching — no plot spoilers
   - **Best watched when:** One-line context (e.g., "late night alone", "with someone who likes dark comedy")

6. **Offer to refine** — After presenting the picks, ask: *"Want me to adjust — more of something, less of something, or a completely different direction?"* Then re-run from step 3 with the new input.

## Output Format

Present recommendations as a clean numbered list. Example structure:

---

**Your mood:** [one-line summary of what you heard]

**1. Movie Title (Year)**
*Director: Name*
**Why it fits:** ...
**What to expect:** ...
**Best watched when:** ...

---

## Guidelines

- Never recommend a film just because it is famous — fit to mood is the only criterion that matters
- If the user's mood is ambiguous or contradictory (e.g., "happy but also want to cry"), lean into the tension — films that hold both tones often feel most satisfying
- For low-energy moods, favour comfort, warmth, and familiarity over challenge
- For high-energy or restless moods, favour momentum, stakes, and strong forward drive
- Always include at least one film that is not the first thing that would come to mind — this is what makes the recommendation feel considered rather than generic
- If the user mentions a specific streaming platform, prioritise films likely available there — but do not make availability guarantees
- Keep rationale language specific and grounded — avoid vague praise like "a cinematic masterpiece"
