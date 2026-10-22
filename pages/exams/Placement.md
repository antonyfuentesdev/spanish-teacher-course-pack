Placement test, finished script (about 15 min; about 1 min on the complete-beginner path) · Rules: 13.9 §1 and the intake chat. This page is the finished, tidy version of the 13.9 §1 scripts; the prompts, clips and decision rules are the same as 13.9 §1, with fixed rephrases, the complete-beginner path and the result wording added. If 13.9 changes a rule, 13.9 wins.

## 0. Before the test (in the learner's language; English shown here)

The intake chat (step 1) comes first: goal, prior Spanish, study plan, typed track, optional target country. Then:

> "Now a short placement check, about 15 minutes. I'll ask you some questions in Spanish, starting very easy and getting harder, and then play three short recordings. It's not a test you can fail: it just shows me where to start. I won't correct you or give hints until the end. If a question is too hard, just say 'no sé' or answer in English; that's useful information too."

Then the bot asks: <b>"Have you studied Spanish before? If not, we can skip the test and start at lesson one."</b>

- "No / I know no Spanish / only hola and gracias" → <b>Complete-beginner path (§1)</b>
- Anything else → <b>Full test (§2–§4)</b>

## 1. Complete-beginner path (test skipped, about 1 minute)

1. The bot speaks English to this learner from the first line (13.8). No ladder prompts and no listening clips: in particular the learner never hears the natural-speed clip.
2. <b>Start: A1, topic A1.1-1</b>, with the normal A1 rules (not "placed": the full A1 lesson-hour minimum applies, 13.11 Gates).
3. Result (English): "Great, we'll start at the very beginning: A1, topic 1, introducing yourself. Lessons are short, and you'll be speaking from the first day. You'll see your progress as a percentage of the level, not as a deadline. At the start of each topic you can take an optional short quiz to skip it if you already know it."
4. Record: Assessments row Type Placement, Level A1, Scores "Test skipped", Skills –, Result Placed, Flag "Beginner (test skipped)".

If the learner later says they know some Spanish after all, the bot offers the full test once at the start of the next call.

## 2. Speaking ladder (full test)

Test mode throughout. Each step has two prompts. The bot gives prompt 1; if the learner struggles, it gives the step's fixed rephrase once, then prompt 2. <b>Two struggles at the same step end the ladder.</b> A step is <b>handled comfortably</b> when both prompts are answered relevantly, at least half of the step's target forms are correct and there was at most one rephrase in the step. The learner's level is the highest step handled comfortably.

<b>Struggle</b> (one prompt): after the rephrase, no relevant answer; or more than half of the target forms wrong; or the answer is mostly in English.

| Step | Target forms | Prompt 1 | Rephrase (once) | Prompt 2 |
| --- | --- | --- | --- | --- |
| 1 (A1) | ser, tener, present -ar, numbers | "¿Cómo te llamas y de dónde eres?" | "Yo me llamo [bot name] y soy de… ¿Y tú?" | "¿Cuántos años tienes y dónde vives?" |
| 2 (A2) | routine verbs, reflexives, time | "Cuéntame un día normal para ti: ¿a qué hora te levantas y qué haces?" | "Por ejemplo: me levanto a las siete, desayuno… ¿Y tú?" | "¿Qué haces los fines de semana?" |
| 3 (B1) | indefinido + imperfecto, pretérito perfecto | "¿Qué hiciste el fin de semana pasado?" | "El sábado o el domingo pasado, ¿adónde fuiste? ¿Qué hiciste?" | "¿Cómo era tu vida hace diez años y qué ha cambiado?" |
| 4 (B2) | conditional, imperfect subjunctive, present subjunctive after esperar que | "¿Qué harías si tuvieras un año libre?" | "Imagina: un año sin trabajo, con dinero. ¿Qué harías?" | "¿Qué esperas que cambie en tu ciudad o en tu trabajo en los próximos años?" |
| 5 (C1) | argument, concession, register | "Algunas personas creen que el teletrabajo debería ser un derecho. ¿Qué opinas? Defiende tu postura." | "¿Estás a favor o en contra? Dame tus razones." | "Yo pienso lo contrario: que cada empresa debe decidir. Convénceme." |

Rules for the bot:
- Wait at least 10 seconds before a rephrase; "a ver…" or "un momento" means wait.
- Personal answers are kept as facts for the Profile (real age, city, job), and are not judged on content.
- An answer of one or two words to a B1+ prompt is not a struggle by itself, but it counts as a struggle if it lacks the step's target forms.
- Pronunciation is noted, never scored.
- Instructions around the prompts are in English for any learner who has not handled step 2 comfortably (13.8); from step 3 on, the bot may give them in Spanish.
- After the ladder ends (or after step 5), the bot says "Thanks! Now some listening." (or "Muy bien, gracias. Ahora vamos a escuchar." after step 2) and moves to the clips.

## 3. Listening check (3 clips, rising speed)

Each clip is read twice; the bot asks the 2 questions after the second reading. Questions may be answered in Spanish or English. A clip is understood when both answers are right.

| Clip | Speed | Text | Questions (key) |
| --- | --- | --- | --- |
| 1 | Slow | "Hola, soy Marta. Vivo en San José, en Costa Rica. Trabajo en un hotel y los domingos voy al mercado con mi hermana." | ¿Dónde trabaja Marta? (en un hotel) · ¿Qué hace los domingos? (va al mercado con su hermana) |
| 2 | Normal | "Ayer quise ir al cine, pero cuando llegué ya no había entradas. Al final me quedé en casa y vi una serie que me recomendó un amigo. La verdad, me gustó más de lo que pensaba." | ¿Por qué no vio la película? (no había entradas) · ¿Qué le pareció la serie? (le gustó más de lo que pensaba) |
| 3 | Natural | "Aunque el gobierno anunció que el transporte público sería gratis para estudiantes, muchas familias dicen que no han notado la diferencia, porque las rutas que usan sus hijos siguen sin funcionar los fines de semana." | ¿Qué se anunció? (transporte gratis para estudiantes) · ¿Por qué las familias no notan la diferencia? (las rutas no funcionan los fines de semana) |

- <b>Clip stop rule (13.9 §1):</b> clip 2 is played only if the ladder reached step 2 or clip 1 was understood; clip 3 only if the ladder reached step 3 or clip 2 was understood. A skipped clip is recorded as not understood. A beginner therefore never hears the natural-speed clip.
- The clips are invented examples; clip 3 describes no real announcement.

## 4. Scoring and placement decision

| Score | Speaking | Listening | Vocabulary | Grammar |
| --- | --- | --- | --- | --- |
| 1 | Single words, memorized phrases | Slow, familiar words (clip 1 not understood) | Survival words | Almost no control |
| 2 | Short sentences on familiar topics | Clip 1 understood | Everyday topics, gaps | Present mostly correct |
| 3 | Connected talk on familiar topics | Clips 1–2 understood | Wide on familiar topics | Past and future used; subjunctive errors |
| 4 | Fluent on most topics, argues a view | Clips 1–3 understood | Broad, some idioms | Subjunctive mostly correct |
| 5 | Flexible, precise, well structured | All 3 understood with ease and detail | Broad, nuanced, register | Consistent control |

- <b>Level</b> = the highest ladder step handled comfortably (A1–C1). If no step was handled comfortably, the level is A1 and the learner starts at A1.1-1 with the normal A1 rules (not "placed").
- The learner starts at the <b>first course of that level</b>; fast-track is offered at the start of session 1 of each topic (Form A, 8/10 and Part B 4/4).
- <b>Locked levels:</b> if the placed level's topics are not in this course pack (13.12), the learner starts at the highest ready level below it, and the bot says so.
- <b>Confirmation:</b> if the first two assessed results at a placed level (fast-track or topic check) are both under 6/10, the learner moves down one level; one fast-track under 8/10 just means the topic is taught normally. The bot tells the learner this before the first fast-track.
- The learner can always ask to start lower.
- Listening does not change the level by itself; if listening is 2 or more points below speaking, the bot notes it as a focus area.
- At the end of the test the bot says the <b>provisional</b> result with 2–3 evidence quotes, so the transcript holds it (13.9 §6).
- <b>Second pass:</b> from the transcript and this page only, before the row is written (13.9 §6). If the two passes give different levels, the lower stands and the row is flagged "Passes disagree".

## 5. Result (said in the learner's language at A1–A2, in Spanish from B1 with English on request)

> "Thanks! You're starting at <b>[level]</b>, in the first topic: <b>[topic title]</b>. Two things you already do well: [strength 1], [strength 2]. Two things we'll work on: [focus 1], [focus 2]. At the start of each topic you can take a short quiz to skip it if you already know it. Your progress shows as a percentage of the level and of the whole plan; it isn't a deadline. Your plan: [days and times]. Does that still work for you?"

No target date or finish date is given.

## 6. Record

- Assessments row: Type Placement, Level, Scores "Ladder step N; listening N/3" (or "Test skipped", Flag "Beginner (test skipped)"), Skills S/L/V/G/P (P = –), Result Placed, Pass 2 total, Flag, Evidence block with one quote per prompt answered and per clip question.
- Sessions row (Type Placement), Profile facts, failed items into the Review queue (intake chat, "Saved after the test").

Evidence example:
```
### E-A-0001
- Step 1 P1 (comfortable): "Me llamo Ken, soy de Canadá."
- Step 1 P2 (comfortable): "Tengo treinta y dos años, vivo en Heredia."
- Step 2 P1 (struggle): "Yo… levanto… seven" (after rephrase)
- Step 2 P2 (struggle): "Fin de semana… playa" → ladder ends at step 2; level A1
- Clip 1 (1/1): "en un hotel" / "market with sister"
- Clip 2 (0/1): "no sé"
```
