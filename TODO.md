# Course Update TODO

Working plan to keep ACS 1710 relevant for students entering the field. Course stays a 14-week, self-paced, 5-module structure — these are fixes/additions within that format. Auth/authorization is intentionally out of scope (covered in the following course).

## Content pattern: lesson exercises vs. graded assessment

The course is moving off Gradescope. Going forward:

- **Lesson-level exercises** become ungraded **self-checks**: a handful of questions written directly in the lesson, with a collapsible `<details><summary>Answer Key</summary>...</details>` block underneath (established in Module 1 Lesson 1). No submission, no infrastructure — self-paced students get instant feedback.
- **Module-level assessment** stays as the real, submitted, instructor-evaluated checkpoint — the existing Quiz 1/2/3 and Final Assessment in `Assessments/`.
- **Open question, not yet decided**: what replaces Gradescope as the *submission mechanism* for those module quizzes and the graded Assignments (01-06)? Out of scope for lesson-content edits — revisit separately.

Any lesson currently pointing to "Answer questions on Gradescope" or a dead Repl.it link should be converted to this self-check pattern.

## Module 1 — Introduction to internet communication patterns, C.R.U.D, and servers

- [x] Lesson 2 (Setting up and Using Flask Servers):
  - [x] Remove the duplicate Flask install step — reorder so venv setup comes first, install Flask once inside it
  - [x] Fix Video 3 link text (currently copy-pasted "Vid 2 - exploring Python's Decorator syntax" instead of describing the `__name__` video)
  - [x] Fix typo: "in front of you terminal prompt" → "your"
  - [x] Add a Learning Outcome bullet covering virtual environments
  - [x] Fill in or remove the empty "What is a virtual environment?" and "Code References" headers (also added Windows activation command and `deactivate`)
- [x] Lesson 1: exercise section still says "Questions coming soon!" — a stale placeholder; write the questions or remove the line (replaced Gradescope submission with a self-check + collapsible answer key, since the course is moving off Gradescope)
- [x] Lessons 3, 4, 6, 7: currently point to "Answer the review questions... on Gradescope" — convert each to the self-check pattern above
- [ ] Lesson 5: currently points to Gradescope, and the Exercises section is headed "Route Variables" only even though the lesson also covers Forms — convert to self-check pattern and cover both topics
- [ ] Standardize the port used in `lesson-2.md`'s boilerplate (currently 3000) against `Assignments/01-Request-Response.md`'s tutorial (shows Flask's default 5000), and add a callout that macOS (Monterey+) reserves port 5000 for AirPlay Receiver — a common silent "server won't start" trap for Mac students

## Module 2 — Creating scalable web applications and templating

- [ ] No content changes planned — content holds up as-is
- [ ] Lessons 1, 3, 4, 5: "Exercises" sections are HTML-commented-out dead Repl.it remnants — convert each to the self-check pattern above (module still keeps its one big graded Assignment as the real checkpoint)

## Module 3 — Building robust services that connect to platforms via APIs

- [ ] New Lesson 4: "Returning JSON Responses with `jsonify`" — cover `jsonify()` and returning status-code tuples (`return data, 201`); renumber existing Lesson 4 (Postman) → 5, Lesson 5 (Requests library) → 6
- [ ] Lesson 5 / Postman lesson: replace remaining `api.icndb.com` references with `api.chucknorris.io` to match the exercise
- [ ] Update Module Learning Objectives to add: "Return properly-formatted JSON responses from a Flask route using `jsonify` and appropriate HTTP status codes."
- [ ] Lessons 1, 3, 5: "Exercises" sections are HTML-commented-out dead Repl.it remnants — convert to the self-check pattern above
- [ ] Lesson 2 (C.R.U.D in APIs): has no Exercises section at all — add a short self-check

## Module 4 — Developing secure, tested, and distributable web applications

- [ ] Update module title/theme to include "tested"
- [ ] New Lesson 4: "Testing Flask Routes with Pytest" — Flask test client, basic `test_*.py`, asserting on status codes and response data. Note: `Assignments/05-Testing.md` already exists and is graded, but currently just says "submit your Flask Testing code completed in class" with no written lesson behind it — self-paced/async students have nothing to learn from
- [ ] Update Module Learning Objectives to add: "Write a Pytest test that verifies a Flask route returns the expected status code and content."
- [ ] `Assignments/05-Testing.md` links to `github.com/Make-School-Labs/Flask-Testing-Starter` — every other assignment (01-04) has migrated to the `Tech-at-DU` org; verify/move this starter repo
- [ ] Lesson 3 (Datetime): exercise links to a dead `repl.it/team/WebArchitecture/Module-401DatetimePractice` — convert to the self-check pattern above

## Module 5 — Introduction to databases and connecting servers to them

- [ ] Split Lesson 1 (Introduction to Databases): keep only the "what is a database" content (fridge analogy etc.)
- [ ] New Lesson 2 (from de-duplicated content): "RESTful Routing & Naming Conventions" — consolidate the plants-resource table/naming rules currently repeated three times in Lesson 1 into one clean pass
- [ ] Lesson 3 (SQL vs NoSQL / MongoDB): fix subtitle mislabeled "Module 3" → "Module 5"; remove dead repl.it link
- [ ] Lesson 4 (Connecting Flask to MongoDB): fix subtitle mislabeled "Module 3" → "Module 5"
- [ ] Lesson 5 (PyMongo C.R.U.D): fix Learning Outcomes (currently copy-pasted from lessons 2/3, don't mention insert/find/update/delete)
- [ ] New Lesson 6: "Deploying Your Flask Application" — **`Labs/deployment-howto.md` already contains a full deployment walkthrough**, so this is a rescue-and-modernize job, not a from-scratch lesson:
  - [ ] Replace Heroku (free tier has required a credit card since late 2022) with a currently-free host such as Render or Railway
  - [ ] Move/link the lesson into Module 5 and reference it from the module readme and top-level README schedule (currently completely unlinked from anywhere)
  - [ ] Keep the MongoDB Atlas connection-string steps, which are still current
- [ ] Update Module Learning Objectives to add: "Deploy a Flask application with a live database connection to a hosting provider."
- [ ] Lesson 1: already has embedded "Practice Examples" (identify RESTful routes) but no answer key and still points to Gradescope — add a collapsible answer key per the self-check pattern above
- [ ] Lessons 2, 4: exercises link to dead `repl.it/team/WebArchitecture/...` and `repl.it/team/WEB11/...` links — convert to the self-check pattern above
- [ ] Lesson 3: has no Exercises section at all — add a short self-check
- [ ] Lesson 5 (PyMongo C.R.U.D): exercise links to a dead `repl.it/team/WebArchitecture/Module-54CRUD-operations-in-PyMongo` link — convert to the self-check pattern above

## Assignments folder

- [ ] `06-Final-Project.md` links to `github.com/Make-School-Labs/WEB-1.1-Final-Project-Starter` — same old-org concern as the Testing assignment above; verify/move this starter repo
- [ ] `02-Forms-Templates.md` points students to "the Repl.It activity we completed during class" (a personal `repl.it/@MeredithMurphy1/...` link) as the reference for refactoring into templates — no written equivalent exists for self-paced/async students who missed that session
- [ ] `03-More-Forms.md` (lines ~94-100): replace the instructor's raw first-person debugging narrative ("I'm not sure why this is, I've searched the internet...") with a clear troubleshooting table for the missing-dependency errors
- [ ] Delete or clearly mark as instructor-only templates: `zzz-Templates.md` (abandoned draft, placeholder `git clone ...` with no URL, empty "Template Inheritance" section, unreferenced anywhere), `Sample_Project.md`, `Sample_Rubric.md` (generic boilerplate, not real course content, unreferenced anywhere)

## Assessments folder

- [ ] `quiz-2-study-guide.md` requires reviewing four personal `repl.it/@MeredithMurphy1/...` links as exam prep — replace with current/working resources
- [ ] `final-assessment.md` hardcodes a specific term's date ("Wed Oct 7") — part of the broader recurring-dates problem below

## Labs / Activities folders (exist but aren't linked from anywhere a self-paced student would find them)

- [ ] `Labs/deployment-howto.md` — see Module 5 deployment item above (rescue from Heroku, link in)
- [ ] `Activities/MongoDB-Setup-Tutorial.md` — empty stub (just a title, no body); finish it or delete it

## Formatting / portability (Notion → GitHub migration artifacts)

- [ ] Dozens of `<aside>` 🤔/💡/🚨 callouts across Modules 2–5 were authored for Notion's UI, where they render as colored callout boxes. On GitHub/plain markdown they render as unstyled plain text, so the intended "pause and think here" visual signal is currently invisible. Consider replacing with GitHub-native blockquote-style callouts (`> **Note:**` etc.)
- [ ] `README.md:3` still has the Notion-era instruction "Hold down SHIFT and press Refresh to get the latest version" — meaningless on GitHub

## Repo-level cleanup (found during review, separate from lesson content)

- [ ] `README.md` "Learning Modules" section links out to stale `notion.site`/`makeschool` URLs instead of the local `Lessons/module-X/lesson-Y.md` files
- [ ] `README.md` has conflicting date sets: course header (Aug 24–Oct 9, 2025), schedule table (ends Oct 7), assignments table (Oct 25–Dec 7), late-policy text ("Mar 3 & Mar 4") — reconcile to one term's dates
- [ ] Hardcoded per-term dates are scattered across `README.md` and `Assessments/final-assessment.md` with no single source of truth, so they drift out of sync between terms — consider a single "current term dates" section that everything else references
- [ ] Remove orphaned `Lessons/module-1/module-5-lesson-4.md` (outdated draft of `module-5/lesson-4.md`, wrong folder, unreferenced)
- [ ] Repo root has ~10 files/folders unrelated to this course (`box-model.html`, `flex-box.html`, `position.html`, `text-styles.html`, `watering.html`, `background-image.html`, `events.html`, `assessment/`, `exercises/`, `projects/`, `images/`) — look like leftovers from a different (prerequisite HTML/CSS) course; confirm and remove if truly unused
