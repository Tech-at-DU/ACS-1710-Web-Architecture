# ACS 1710 Web Architecture

This syllabus is a living document! Check the [GitHub repo](https://github.com/Tech-at-DU/ACS-1710-Web-Architecture) for the latest version.

## Course Description

This course is designed to introduce students to the Flask web framework. Students will learn language independent patterns that are repeated across many common servers. The course will cover topics including the request-response cycle, server-side templating, APIs, databases, & unit testing, to help students to build the skills necessary to create custom web sites.

This course covers language-independent web server frameworks and patterns in full-stack web design. Students will use their prior knowledge in HTML, CSS, and JavaScript to build the front-end of a simple web application, and then will learn new concepts to write a supporting back-end. This course covers the request-response cycle, server-side templating, parsing data from an HTML form, HTTP methods, and using APIs. More advanced concepts include document-based databases and controller testing.

<!-- ### 👉 [ Introduction to WEB 1.1 (Web Architecture)](https://handsome-air-ad0.notion.site/Introduction-to-WEB-1-1-Web-Architecture-eb65692e73e04a7784e6b39b8c962488) 🚀 -->

## Prerequisites:

1. ACS 1700 (Web Foundations)

## Learning Outcomes

By the end of the course, you will be able to ...

1. Use Flask routes & route variables to create web pages with dynamic content.
1. Use forms & Jinja2 templates to take user input and display a result.
1. Make API calls & use/analyze the JSON data to show a result to the user.
1. Read and write to the MongoDB database using the PyMongo Object Document Mapper (ODM).
1. Implement Flask route tests to verify the correctness of routes.
1. Understand how the “create, read, update, deletion” (C.R.U.D) operations form the basis of user interactions in web architecture.

## Schedule

**Course Dates & Class Times:** set per term — check with your instructor for this term's specific dates and meeting times.

This course is self-paced across 14 weeks. Attendance is still required — the pacing below is a recommendation to help you stay on track, not a hard deadline except where noted.

| Week | Pacing Recommendation |
|:--:|:--|
| 1  | [Module 1](Lessons/module-1/) |
| 2  | Finished [Homework 1: Request/Response](Assignments/01-Request-Response.md) |
| 3  | [Module 2](Lessons/module-2/) |
| 4  | Finished [Homework 2: Forms](Assignments/02-Forms-Templates.md) |
| 5  | Finished [Quiz 1](Assessments/quiz-1-study-guide.md) **(hard deadline — closes end of week)** |
| 6  | [Module 3](Lessons/module-3/) |
| 7  | Finished [Homework 3: More Forms](Assignments/03-More-Forms.md) |
| 8  | Finished [Homework 4: APIs](Assignments/03-APIs.md) |
| 9  | Finished [Quiz 2](Assessments/quiz-2.md) **(hard deadline — closes end of week)** |
| 10 | [Module 4](Lessons/module-4/) |
| 11 | Finished [Homework 6: Testing](Assignments/05-Testing.md) |
| 12 | [Module 5](Lessons/module-5/) |
| 13 | Finished [Homework 5: Databases](Assignments/04-Databases.md) |
| 14 | Finished [Quiz 3](Assessments/quiz-3-study-guide.md), the [Final Project](Assignments/06-Final-Project.md), and the [Final Assessment](Assessments/final-assessment.md) |

Quizzes can be retaken once, with the final grade being the average of the two scores. Students who complete all assignments with a score of 3 or higher and earn 80% or greater on Quizzes 1 & 2 **automatically pass Quiz 3** and won't be required to take it! 🤩

Students falling behind should connect with the instructor for help staying on pace. Any assignment not completed by the end of the term will be scored as a 0, except for extenuating circumstances (see the Late Assignment Policy below).

## Learning Modules

This course has been broken down into 5 modules for students to approach at their own pace. See the **schedule** below for recommendations on where you should be at in terms of content completion to help assess your pace.

### Although this course has self-pacing elements--attendance is still a requirement! We will be doing activites, checking-in, and learning as a class!

#### MODULE 1: [Introduction to internet communication patterns, C.R.U.D, and servers](Lessons/module-1/readme.md)

1. [Introduction to the Request/Response Cycle](Lessons/module-1/lesson-1.md)
2. [Setting up and Using Flask Servers](Lessons/module-1/lesson-2.md)
3. [Introduction to C.R.U.D](Lessons/module-1/lesson-3.md)
4. [`GET` vs `POST`](Lessons/module-1/lesson-4.md)
5. [Working with Route Variables and Forms](Lessons/module-1/lesson-5.md)
6. [Interacting with Form Data in Flask](Lessons/module-1/lesson-6.md)
7. [Understanding `*args` and `**kwargs`](Lessons/module-1/lesson-7.md)

#### MODULE 2: [Creating scalable web applications and templating](Lessons/module-2/readme.md)

1. [Templating](Lessons/module-2/lesson-1.md)
2. [Named Parameters](Lessons/module-2/lesson-2.md)
3. [Conditional Rendering with Templates](Lessons/module-2/lesson-3.md)
4. [Loops in Templates](Lessons/module-2/lesson-4.md)
5. [Creating Reusable Components via Template Inheritance](Lessons/module-2/lesson-5.md)

#### MODULE 3: [Building robust services that connect to platforms via API's](Lessons/module-3/readme.md)

1. [Introduction to APIs](Lessons/module-3/lesson-1.md)
2. [C.R.U.D in API's](Lessons/module-3/lesson-2.md)
3. [Working with JSON Objects](Lessons/module-3/lesson-3.md)
4. [Returning JSON Responses with `jsonify`](Lessons/module-3/lesson-4.md)
5. [Testing API Routes with Postman](Lessons/module-3/lesson-5.md)
6. [Using the Requests Library to Generate User Requests](Lessons/module-3/lesson-6.md)

#### MODULE 4: [Developing secure, tested, and distributable web applications](Lessons/module-4/readme.md)

1. [Working with Virtual Environments and the `requirements.txt` File](Lessons/module-4/lesson-1.md)
2. [Creating and Managing Environment Variables with `dotenv`](Lessons/module-4/lesson-2.md)
3. [Leveraging the Datetime Library](Lessons/module-4/lesson-3.md)
4. [Testing Flask Routes with Pytest](Lessons/module-4/lesson-4.md)

#### MODULE 5: [Introduction to databases and connecting servers to them](Lessons/module-5/readme.md)

1. [Introduction to Databases](Lessons/module-5/lesson-1.md)
2. [RESTful Routing & Naming Conventions](Lessons/module-5/lesson-2.md)
3. [SQL vs NoSQL and Introduction to MongoDB](Lessons/module-5/lesson-3.md)
4. [Connecting a Flask Server to MongoDB Cluster](Lessons/module-5/lesson-4.md)
5. [Performing C.R.U.D Operations with PyMongo](Lessons/module-5/lesson-5.md)
6. [Deploying Your Flask Application](Lessons/module-5/lesson-6.md)
7. [Pymongo Todo List](Assignments/module-5-tutorial.md)



## Evaluation

**To pass this course, you must**: 

- Earn an average score of 2 on each of the assignment rubrics. Each section's score will be determined by your performance on that week's assignment. The last section's score will be determined by your adherence to deadlines, class participation, & completion of the readings.
- Pass the 3 quizzes by earning an average score of >70%.
- Abide by the Attendance Policy.

## Attendance Policy

Each student will be allowed **2 (two) unexcused absences** and **2 (two) excused absences** per course per term. An absence is excused if you reach out to your instructor prior to class to explain why you can't make it. If you exceed the total number of allowed absences, you will be withdrawn from the course.

## Late Assignment Policy

Since this class uses a self-pacing model, there will be no late assignments. However, assignments must be turned in by the end of the term or else they will be scored as a 0! 

Exceptions will only be made to this rule for extenuating circumstances such as prolonged illness. Please reach out to the instructor if something like this happens to you.

## Academic Honesty Policy

At Make School, we highly encourage collaboration between students on assignments. Working with other people is the best way to learn!

However, there's a big difference between **collaboration** (writing code together with another person) and **plagiarism** (copying code from a classmate or outside source without providing proper attribution). 

Here are some guidelines to follow in order to avoid plagiarism:

1. If you are looking at an outside source for help, **close the window** containing the code before writing your own solution.
1. Do not write down a line of code unless you **completely understand** how it works. (This is true even if the source you're referencing is the lesson slides/examples/etc!)
1. If your code is still similar to an outside source or another student's, **provide attribution** by adding a comment to your code explaining where it was taken from.
<!-- 
We take academic honesty very seriously at Make School. The consequences for violating the policy are as follows:

- You will be required to write a [Self-Reflection Letter](https://docs.google.com/document/d/140_PHfDh7gu33OZI_caxEtvNzAlAepjnGcbQcXZ-MRo/edit?usp=sharing) to reflect on how your actions affected others.
- If this is your first offense, you may be permitted to redo the assignment for a reduced grade (at the instructor's discretion).
- The incident will be added to your permanent record at Make School and you may be placed on a Participation Improvement Plan (PIP).

For subsequent offenses, more serious consequences may be considered. For more information, please see [Make School's academic honesty policy](https://make.sc/academic-honesty-policy). -->

<!-- ## Information Resources

Any additional resources you may need (online books, etc.) can be found here. You can also find additional resources through the library linked below:

- [make.sc/library](http://make.sc/library) -->

<!-- ## Make School Course Policies

- [Program Learning Outcomes](https://make.sc/program-learning-outcomes) - What you will achieve after finishing Make School, all courses are designed around these outcomes.
- [Grading System](https://make.sc/grading-system) - How grading is done at Make School
- [Code of Conduct, Equity, and Inclusion](https://make.sc/code-of-conduct) - Learn about Diversity and Inclusion at Make School
- [Academic Honesty](https://make.sc/academic-honesty-policy) - Our policies around plagerism, cheating, and other forms of academic misconduct
- [Attendance Policy](https://make.sc/attendance-policy) - What we expect from you in terms of attendance for all classes at Make School
- [Course Credit Policy](https://make.sc/course-credit-policy) - Our policy for how you obtain credit for your courses
- [Disability Services (Academic Accommodations)](https://make.sc/disability-services) - Services and accommodations we provide for students
- [Online Learning Tutorial](https://make.sc/online-learning-tutorial) - How to succeed in online learning at Make School
- [Student Handbook](https://make.sc/student-handbook) - Guidelines, policies, and resources for all Make School students -->
