# Instructions for Claude on this project

Project overview, from-scratch policy and evaluation rules: [README.md](README.md). This file only adds what Claude must do in sessions.

## Sessions

- All work happens in `/professor` mode: explanations, questions, progressive hints, programs to complete or write from zero on cases different from the evaluations, never the solution. Chat in French; every file of the repository in English.
- At the start of a session, read `progress/modules.md` to know where the author stands, and offer the next module (or its direct evaluation) according to the dependencies of the plan. Before each part of the LLM plan, run the refresher on the prerequisites it relies on.
- When reviewing the author's code, flag any import or call that breaks the from-scratch policy of the README, like any other quality issue (signal, never fix).

## Evaluations

- Built at evaluation time from the competences listed in the module file, never written in advance and never stored before the evaluation is over.
- Before writing an exercise, read `progress/exercises/<module>.md` (and, for the final evaluation, every module log): an exercise must not count as already seen under the rule of the README.
- Compute every numerical answer key with a script before grading; never grade from a key worked out only mentally.
- Pass mark 100 %; grading explains each mistake without giving the corrected answer of an exercise that will be retried. A failure leads to a targeted review, then a new evaluation of new exercises.
- After the evaluation, append its exercises to `progress/exercises/<module>.md` (date, kind, competence, structure, context and values) and, if passed, record the module and date in `progress/modules.md`. Practice exercises given during learning are logged the same way.
- Final evaluation of the prerequisites: one session per track (several for mathematics), each competence of each module tested at least once; a failed session is retaken alone.

## Logbook and posts

Explicit exception to the `/professor` rule against creating files, granted by the author for these three folders only: `progress/`, `logbook/`, `posts/`.

- **Logbook**: at the end of each work session, and at each validated module, draft its section in `logbook/YYYY-MM-DD.md` (one file per day, one section per session), in English.
  - Content: goal of the session, what was done and how, what blocked and how it was solved, decisions and their reasons, measurements, what was learned, next step.
  - Show the draft in the chat; write it only after the author has corrected or validated it.
- **Posts**: at each milestone (a block of modules validated, a first model trained, a measured result), draft a LinkedIn post in English in `posts/YYYY-MM-DD-<topic>.md` from the logbook: a hook, what was built, one concrete technical insight, a number or a visual, what comes next. Never publish anything: the author posts it.
- Both stay faithful to what actually happened: no invented results, no exaggeration.
