# Course Update TODO

Working plan to keep ACS 1710 relevant for students entering the field. Course stays a 14-week, self-paced, 5-module structure — these are fixes/additions within that format. Auth/authorization is intentionally out of scope (covered in the following course).

## Module 1 — Introduction to internet communication patterns, C.R.U.D, and servers

- [ ] Lesson 2 (Setting up and Using Flask Servers):
  - [ ] Remove the duplicate Flask install step — reorder so venv setup comes first, install Flask once inside it
  - [ ] Fix Video 3 link text (currently copy-pasted "Vid 2 - exploring Python's Decorator syntax" instead of describing the `__name__` video)
  - [ ] Fix typo: "in front of you terminal prompt" → "your"
  - [ ] Add a Learning Outcome bullet covering virtual environments
  - [ ] Fill in or remove the empty "What is a virtual environment?" and "Code References" headers

## Module 2 — Creating scalable web applications and templating

- [ ] No changes planned — content holds up as-is

## Module 3 — Building robust services that connect to platforms via APIs

- [ ] New Lesson 4: "Returning JSON Responses with `jsonify`" — cover `jsonify()` and returning status-code tuples (`return data, 201`); renumber existing Lesson 4 (Postman) → 5, Lesson 5 (Requests library) → 6
- [ ] Lesson 5 / Postman lesson: replace remaining `api.icndb.com` references with `api.chucknorris.io` to match the exercise
- [ ] Update Module Learning Objectives to add: "Return properly-formatted JSON responses from a Flask route using `jsonify` and appropriate HTTP status codes."

## Module 4 — Developing secure, tested, and distributable web applications

- [ ] Update module title/theme to include "tested"
- [ ] New Lesson 4: "Testing Flask Routes with Pytest" — Flask test client, basic `test_*.py`, asserting on status codes and response data
- [ ] Update Module Learning Objectives to add: "Write a Pytest test that verifies a Flask route returns the expected status code and content."

## Module 5 — Introduction to databases and connecting servers to them

- [ ] Split Lesson 1 (Introduction to Databases): keep only the "what is a database" content (fridge analogy etc.)
- [ ] New Lesson 2 (from de-duplicated content): "RESTful Routing & Naming Conventions" — consolidate the plants-resource table/naming rules currently repeated three times in Lesson 1 into one clean pass
- [ ] Lesson 3 (SQL vs NoSQL / MongoDB): fix subtitle mislabeled "Module 3" → "Module 5"; remove dead repl.it link
- [ ] Lesson 4 (Connecting Flask to MongoDB): fix subtitle mislabeled "Module 3" → "Module 5"
- [ ] Lesson 5 (PyMongo C.R.U.D): fix Learning Outcomes (currently copy-pasted from lessons 2/3, don't mention insert/find/update/delete)
- [ ] New Lesson 6: "Deploying Your Flask Application" — deploy a Mongo-backed Flask app to a free host (Render), set `MONGO_URI` as an environment variable on the host; course capstone
- [ ] Update Module Learning Objectives to add: "Deploy a Flask application with a live database connection to a hosting provider."

## Repo-level cleanup (found during review, separate from lesson content)

- [ ] `README.md` "Learning Modules" section links out to stale `notion.site`/`makeschool` URLs instead of the local `Lessons/module-X/lesson-Y.md` files
- [ ] `README.md` has conflicting date sets: course header (Aug 24–Oct 9, 2025), schedule table (ends Oct 7), assignments table (Oct 25–Dec 7), late-policy text ("Mar 3 & Mar 4") — reconcile to one term's dates
- [ ] Remove orphaned `Lessons/module-1/module-5-lesson-4.md` (outdated draft of `module-5/lesson-4.md`, wrong folder, unreferenced)
