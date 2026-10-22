<callout icon="📘" color="blue_bg">
The essentials of the course: voice-first Spanish, CEFR A1 to C1, for adult learners, in neutral Latin American Spanish (Mexico, Costa Rica, Colombia, Panama). Course and topic map from AVE Global (Instituto Cervantes); session flow, exams and scales modelled on published programs; grammar, lexis and sound assignment per topic is our own. Badges are bot-assessed, never an official certificate.
</callout>

## How this pack fits together

- <b>This page:</b> levels, topic order, how a topic runs, how progress and passing work, where progress is recorded
- <b>Course rules (13.1–13.11):</b> 13.1 Syllabus (all 48 topics, hours, pacing) · 13.2 Topic format (sessions, the 30-minute sequence, materials checklist) · 13.3–13.7 Worked examples (one per level) · 13.8 Teaching notes (correction, voice habits, English use, regional awareness) · 13.9 Rubrics (placement, topic checks, level exams, graduation, scoring integrity) · 13.10 Spaced review schedule · 13.11 Progress tracking (file format, gates, learner-facing words)
- <b>13.12 Topic materials:</b> one page per topic, 48 in all, each with Forms A–D of its topic check
- <b>13.13 Exam papers:</b> administration and scoring guide, placement test, level exam papers A1–C1 (Forms 1–3) and the C1 graduation oral
- References like "13.9 §3" or "13.11 Gates §5" point to the course rules pages of this pack

## Where progress lives

Every learner record goes in <b>one progress file on the bot's own computer</b>, <code>/workspace/spanish-teacher/progress.md</code>, written as plain markdown tables in <b>schema v2</b> (exact headers, IDs and allowed values in 13.11). That file is the <b>source of truth</b>. Bot memory holds only a short summary per learner: level, current topic, top errors and next review date, plus the learner profile facts. Nothing is stored in an external service: no database, spreadsheet or other app. Chat messages and Pages are views of the file, not records.

| Tracked item | Source of truth (progress file) | Also in memory | Written when | Written by |
| --- | --- | --- | --- | --- |
| Learner profile: name, native language, goal, target country (awareness only), study plan (days and hours), planned lessons per week, typed track, age, city, job or studies, level start, lowered targets | Profile | Copy of goal, native language, target country, age, city, job or studies | At intake; again whenever the learner changes one | Placement test, Progress update |
| Placement result | Assessments, type Placement, with Evidence | Level and current topic | At the end of the intake call | Placement test, Progress update |
| Session log, including lesson hours, learning hours and the drill score | Sessions, one row per call or self-reported outside activity, keyed by start time | No | After every call, from the transcript | Progress update; Daily reconcile fills gaps |
| Topic checks (Form, attempt, fast-track) | Assessments, type Topic check, with Evidence and second-pass total | No | After the call that included the check | Progress update |
| Level exams (A1–C1): every paper, the retention set and both scoring passes | Assessments, type Level exam: one row per sitting; a retake is a new row | Level, updated on a pass | After the last paper; second pass the next day | Level exam, Progress update, Daily reconcile |
| One-month checks (30 days after each level pass) | Assessments, type Retention check; Milestones (Retention passed or Refresher due) | No | After the check call | Progress update |
| C1 graduation oral (per-criterion scores, pass conditions, both passes) | Assessments, type Graduation; Graduation Milestones row citing it and the gate check | Level set to "C1 graduated" | After both scoring passes | Graduation exam, Progress update, Daily reconcile |
| Pronunciation drill checks (recorded only) | Sessions, Drill column | No | After each session with a drill | Progress update |
| Skill scores 1–5 (S/L/V/G; P blank: excluded from pass decisions by design, feedback only) | Assessments, Skills column of placement, topic check and level exam rows | No | With that assessment row | Progress update |
| Evidence quotes for every score | Evidence section after the Assessments table (E-A-nnnn) | No | With the assessment row | Progress update |
| Review queue | Review queue, one row per active item (13.10); retired items in <code>progress-archive.md</code> | Next review date and item count only | After every call; read before every session | Progress update; Due-word reviews routine |
| Top errors | Review queue items of type Error, with miss count | Top 3 | After every call | Progress update |
| Level, Level % and Overall % (what the learner sees) | Sessions (Level %, Overall %) and Weekly log; formulas in 13.11 | Level | After every call and weekly | Progress update, Weekly progress summary |
| Gate status (hours, sessions, spacing, retention) | Worked out from Sessions, Assessments and Milestones; written in Milestones "Gate check" and the Weekly log | No | When a gate is checked; weekly | Progress update, Weekly progress summary |
| Weekly summary | Weekly log, one row per week | No | Once a week | Weekly progress summary routine (shown in chat, may also be a Page) |
| Badges, course ups, level ups, move downs | Milestones, citing the Assessments IDs they depend on | Level and current topic | When a gate in 13.11 is met | Progress update |
| Backups | <code>/workspace/spanish-teacher/backups/progress-YYYY-MM-DD.md</code>, last 14 days | No | First write of each day | Progress update (write procedure, 13.11) |

<b>File lifecycle</b>

- <b>Created fresh at intake</b> on each copy of the bot: the file is not part of the template. Course setup creates it empty (13.11 File template); intake fills the header's learner name and time zone, the Profile, the Placement row in Assessments with its Evidence (for a self-declared beginner, their answer), and a Sessions row for the placement test or short first lesson if one took place; the other tables start empty
- <b>Read before each session</b> to pick the topic, due reviews, pending retakes and gate status. This may or may not work inside a live call, so the <b>next session brief</b> routine always posts all of it in chat first (built-in fallback; 13.11 design assumption A1)
- <b>Written after each call</b> from the transcript with the write procedure in 13.11 (temporary file, validation, daily backup, replace; rows keyed by call start time so nothing is duplicated); then the memory summary. Nothing relies on a specific write trigger; built-in fallbacks: a <b>daily reconcile</b> routine and the next session's opening step write anything missing ("listo" is optional). A check result is said aloud in the call so it is in the transcript, and stays <b>pending</b> until saved, never lost (13.11 Pending results; assumptions A2, A3)
- <b>Rows are added, not overwritten</b>, except the Profile table and Review queue rows, which are updated in place. A correction is a new row with a note
- <b>On conflict</b> the file wins; the bot corrects memory to match
- <b>Reserved names:</b> only the tutor writes <code>progress.md</code>, <code>progress-archive.md</code> and <code>backups/</code>; one tutor copy per learner account, because all Bots on an account share one computer
- Table formats: 13.11 Progress tracking. Scoring rules: 13.9 Rubrics. Queue rules: 13.10

## 1. Level structure (from AVE Global)

- CEFR A1 to C1 in <b>16 courses</b>: A1.1, A1.2, A2.1, A2.2, B1.1–B1.4, B2.1–B2.4, C1.1–C1.4
- <b>48 topics</b>, 3 per course, in AVE Global's order — [AVE Global](https://ave.cervantes.es/aveglobal/cursos-espanol-en-linea-ave-global.html), [AVE curriculum (Cervantes Shanghai)](https://shanghai.cervantes.es/es/cursos_espanol/cursos_en_linea_espanol/cursos_ave.htm)
- Each topic: one main grammar focus plus supporting grammar, lexis and chunks, and one sound (13.1). Not yet mapped to the Instituto Cervantes Plan Curricular (its pages could not be opened); that check is future work

## 2. Topic order (official AVE Global topic names)

- <b>A1.1:</b> 1. Primeros contactos. Saludos y datos personales · 2. La familia y los amigos. Descripción física y estados de ánimo · 3. La alimentación
- <b>A1.2:</b> 4. La ciudad y el transporte · 5. Un día normal. Horarios, hábitos y costumbres · 6. El tiempo libre. Organizar actividades de ocio
- <b>A2.1:</b> 1. Nuestra experiencia. Hablar de nuestro pasado personal y profesional · 2. Ir de compras. Necesidades y gustos · 3. Nuestras biografías. Relatar y describir el pasado
- <b>A2.2:</b> 4. Viajes. Turismo y planes de vacaciones · 5. Las opiniones. Expresar el punto de vista · 6. Los sentimientos. Expresar emociones y valoraciones
- <b>B1.1:</b> 1. Encuentros. Presentarnos y conversar sobre nosotros mismos · 2. Cambios. Hablar del pasado y su relación con el presente · 3. Historias. Narrar el pasado e imaginar el futuro
- <b>B1.2:</b> 4. La salud. Comida y vida sana. Enfermedades y remedios · 5. La ciudad y la vivienda. Compras. Trámites administrativos · 6. Los viajes y los servicios turísticos. Climas y lugares
- <b>B1.3:</b> 7. Un paseo cultural: literatura, escultura y música · 8. El poder de la imagen. Moda y publicidad · 9. El mercado laboral. Empresas en España e Hispanoamérica
- <b>B1.4:</b> 10. Relaciones y protocolo en actos sociales · 11. Medio ambiente. Campo y ciudad · 12. Aprender idiomas. La conciencia intercultural
- <b>B2.1:</b> 1. ¿Nos conocemos? Carácter y personalidad. Formación y experiencia laboral · 2. ¡Qué tiempos aquellos! Historias, sucesos, relatos y acontecimientos · 3. Mirar hacia delante. Planes, intereses y deseos. Hechos futuros posibles e imposibles
- <b>B2.2:</b> 4. Busco un lugar. Descripción de pueblos y ciudades · 5. Me interesa tu opinión. Participación en la sociedad · 6. Estoy intrigado. Establecer hipótesis
- <b>B2.3:</b> 7. ¿Qué me recomiendas? Sugerencias, peticiones y consejos · 8. Dicen que dicen… Contar qué dicen, sugieren o aconsejan otras personas · 9. ¡Qué arte tiene! Manifestaciones artísticas del mundo hispano
- <b>B2.4:</b> 10. Si lo hubiera sabido… Condiciones hipotéticas y reclamaciones formales · 11. Alimenta que da gusto. Describir y valorar la gastronomía hispana · 12. ¡Hagan juego! Juegos hispanos. Concursos, ofertas de trabajo, condiciones y reglas en Internet
- <b>C1.1:</b> 1. Protagonistas: nosotros. Medios de comunicación. Biografías y autobiografías · 2. Para eso están los amigos. Enfermedades y hábitos de salud. Ritos funerarios · 3. Pero… ¿qué se habrán creído? Reclamaciones relacionadas con la vivienda
- <b>C1.2:</b> 4. Se hace camino al andar. La emigración y los intelectuales hispanos en el exilio · 5. Aquí hay trabajo. Comunicarse con éxito en el mundo laboral · 6. Cada maestrillo con su librillo. La evolución de la enseñanza. Cambios personales
- <b>C1.3:</b> 7. Busque, compare y si encuentra algo mejor… Consumo y publicidad · 8. Viajar y viajar. Rutas históricas, turísticas y culturales hispanas · 9. La historia me absolverá. Panorama político y literario de Iberoamérica
- <b>C1.4:</b> 10. Un futuro verde. Ecología, recursos naturales, fuentes de energía y contaminación · 11. El español y su literatura. Instituciones de la lengua y el fomento de la lectura · 12. Dele que DELE. El humor. El DELE C1

## 3. Topic flow (from Aula Internacional / Nuevo Prisma)

Input → noticing grammar → practice → speaking task → pronunciation drill → spaced review. Timings, what each of a topic's 10–16 sessions is for, consolidation sessions per course and the materials checklist are in 13.2.

- Sources: [Aula Internacional Plus](https://difusion.com/catalogo/aula-internacional-plus/), [Nuevo Prisma A1 index](https://edinumen.es/muestras/nprisma/indice_nprisma_alumno_a1.pdf)

## 4. Voice patterns (from Language Transfer and Pimsleur)

- <b>Pause, think, answer aloud:</b> the bot asks the learner to build a sentence before giving it — [Language Transfer](https://www.languagetransfer.org/complete-spanish)
- <b>Graduated interval recall:</b> earlier items come back at growing intervals (13.10) — [Pimsleur method](https://www.pimsleur.com/the-pimsleur-method/)
- <b>Short spoken sessions:</b> about 30 minutes, voice-first; at most 2 new-content lesson sessions a day, combined into sittings of up to 2 hours with breaks and review (13.2)
- <b>Optional typed track:</b> 5 extra minutes per session in the chat after the call (short texts to read, short replies to type, a little dictation), so spelling, accents and basic reading can be taught and tested. It can be switched on or off any time; each topic's graded writing task has a named session (13.2). Learners who skip it get a spoken-only badge (13.9). The reading and writing group of a level exam needs a minimum number of graded writing tasks at that level first (13.9 §3)
- Voice protocols (error vs audio signal, ending check, turn-holding, language setting) are in 13.8

## 5. Placement (SIELE style)

- One adaptive, multilevel speaking and listening test (\~15 min); sets the level, the learner starts at the first course of it and fast-tracks with early topic checks; pronunciation is not used; scripts and the definition of a struggle are in 13.9 §1. A complete beginner can skip the test and start at A1.1-1. Placement only opens fast-tracks (optional, at the start of each topic's session 1); a fast-track under 8/10 just means the topic is taught normally, and two results under 6/10 at a placed level lead the bot to offer a move down one level, never an automatic one (13.11) — [SIELE format](https://examenes.cervantes.es/es/siele/como), [score bands](https://siele.org/en/examenes)

## 6. Pronunciation (CEFR)

- Judged by <b>how easy the learner is to understand</b>, not native accent: a 0–2 check per drilled feature, and the CEFR scale for level exams (13.9)
- Because the bot may only hear a transcript, pronunciation is excluded from placement, promotion and all pass decisions by design: the course does no audio-rating test, and pronunciation is coached and reported for feedback only — [CEFR phonological competence](https://www.coe.int/en/web/common-european-framework-reference-languages/phonological-competence)

## 7. Progress, passing and time gates (DELE / AVE Global)

- <b>Topic:</b> pass the topic check at <b>60%</b>
- <b>Topic check:</b> 10 points (6 controlled, 4 speaking-task criteria), template in 13.9
- <b>Course:</b> 3 topic checks passed and both consolidation sessions done (measurable; replaces AVE's 65%-of-activities rule)
- <b>End-of-level exam (A1, A2, B1, B2, C1):</b> listening and speaking for everyone; reading and writing (texts in chat, typed answers, short dictation) for typed-track learners
- <b>Pass rule: combined, like real DELE.</b> At least 60% in each paired group, papers added together: listening + speaking ≥ 30/50 (this moves the learner up) and, on the typed track, reading + writing ≥ 30/50 (this only decides the four-skill badge; it never blocks a level up) — [DELE structure](https://examenes.cervantes.es/es/dele/como)
- Badges say what was tested: "Spoken Spanish \[level\]" or, with the typed track, "listening, speaking, reading and writing"; always "bot-assessed", never an official certificate
- Details in 13.9 and 13.11, with can-do exit statements per level
- <b>Anti-rush gates:</b> based mainly on lesson hours and sessions (75% of a level's plan lesson hours before its exam; 25% at a placed level), at most 2 lesson sessions a day, limited fast-tracks and retakes with spacing, an exam memory check (7/10) inside every level exam, a one-month check (6/10) 30 days after every level pass (so level passes are at least 30 days apart), and a modest 3-week minimum per level. Full rules: 13.11 Gates
- <b>What learners see:</b> their CEFR level, topics done and lesson hours, percent progress in the level (after every call) and percent progress through the whole course, Overall % (weekly and on request; formulas in 13.11), capped so neither reaches 100% before the gates are met and recorded; milestone messages for early wins. No target dates, calendar promises or time ranges, even when the learner asks (13.11)
- <b>Scoring integrity:</b> fixed item forms, an evidence quote for every score, a second scoring pass, and no record can be changed by a learner's request (13.9 §6)
- <b>Tracking:</b> built-in features only. The bot's memory keeps a short summary per learner; a progress file on the bot's computer keeps one row per session and the review queue. Both are updated after every call from the transcript; placement, topic checks, level exams, retention checks and graduation go in the file's Assessments table, drill scores in the Sessions row ("Where progress lives" above; 13.10, 13.11)

## 8. Graduation (C1)

- Presentation with mediation, interview and informal negotiation, as in the DELE C1 oral paper (checked against the search-index copy of the official 2024 exam guide; live page unreachable) — [DELE C1 guide](https://examenes.cervantes.es/sites/default/files/Guia_examen_DELE_C1_2024_0.pdf)
- Achievement badge, not an official DELE or SIELE credential
- <b>Scoring:</b> 3 tasks × 25 points = 75. Pass = total ≥ 45, every task ≥ 13, no criterion at 1, Accuracy ≥ 3 in at least 2 tasks; 60 or more = distinction; second scoring pass the next day (13.9 §4)
- Graduation needs every gate in 13.11 Gates §8 recorded in the progress file; the bot never announces it earlier
