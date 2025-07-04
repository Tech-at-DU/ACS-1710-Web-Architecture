# ACS 1710 Web Architecture

<span class="refresh-instructions">This syllabus is a living document! Hold down the `SHIFT` key and press `Refresh` to get the latest version.</span>

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

**Course Dates:** August 25 – October 10, 2025

**Class Times:** Monday and Wednesday, 1:30 PM – 4:00 PM

| Class | Date | Pacing Recommendations (Complete all lessons up to - ) |
|:---:|:--:|:-----:|
|  - | Week 1      | - |
|  1 | Mon, Aug 25 | [Module 1](Lessons/module-1/) |
|  2 | Wed, Aug 27 | [Finished Module 1 Assignment](Assignments/01-Request-Response.md)  |
|  - | Week 2      | - |
|  3 | Mon, Sep  1 | ******LABOR DAY****** |
|  4 | Wed, Sep  3 | [Module 2](Lessons/module-2/) |
|  - | Week 3      | - |
|  5 | Mon, Sep  8 | [Finished Module 2 Assignment](Assignments/02-Forms-Templates.md) |
|  6 | Wed, Sep 10 | **Finished Quiz 1 (HARD DEADLINE - CLOSES END OF WEEK)** |
|  - | Week 4      | - |
|  7 | Mon, Sep 15 | [Module 3](Lessons/module-3/) |
|  8 | Wed, Sep 17 | [Finished Module 3 Assignment](Assignments/03-More-Forms.md) |
|  - | Week 5      | - |
|  9 | Mon, Sep 22 | **Finished Quiz 2 (HARD DEADLINE - CLOSES END OF WEEK)** |
| 10 | Wed, Sep 24 | [Module 4](Lessons/module-4/) |
|  - | Week 6      | - |
| 11 | Mon, Sep 29 | [Finished Module 4 Assignment](Assignments/03-APIs.md) |
| 12 | Wed, Oct  1 | [Module 5](Lessons/module-5/) |
|  - | Week 7      | - |
| 13 | Mon, Oct  6 | LAB DAY |
| 14 | Wed, Oct  8 | [Finished Module 5 Assignment](Assignments/04-Databases.md) |

## Assignments
Students will complete assignments at their own pace. 

Assignments **must be turned in via [Gradescope](https://gradescope.com) for credit!**

### Assignments should be completed by the recommended date in the above **schedules** section. Students falling behind should connect with the instructor for help staying on pace!

### Any assignments not complete by the final day of class (Wed, Mar 3 & Thu, Mar 4) will be given a score of **0**.

Quizzes can be found on [Gradescope](https://gradescope.com) for credit during the week of their listing.

### Quizzes have a **HARD DEADLINE** date and will close on the Friday of its listed week. 

Quizzes can be retaken once, with the final grade being the average of the two final scores. 

### Students that have completed all assignments with a score of 3 or higher and earned an 80% or greater on their quizzes **AUTOMATICALLY PASS QUIZ 3** and will not be required to take it! 🤩

| Topic | Pacing Date | Assignment |
| :--: | :------------: | :----: |
| 1 | Tue, Oct 25 | [Module 1 Assignment: Request/Response](Assignments/01-Request-Response.md) |
| 2 | Tue, Nov  1 | [Module 2 Assignment: Forms & Templates](Assignments/02-Forms-Templates.md) |
| 3 | Thu, Nov  3 | [**Quiz 1**](Assessments/quiz-1-study-guide.md) |
| 4 | Thu, Nov 10 | [Module 3 Assignment: More Forms](Assignments/03-More-Forms.md) |
| 5 | Tue, Nov 15 | [**Quiz 2**](Assessments/quiz-2.md) |
| 6 | Thu, Dec  1 | [Module 4 Assignment: APIs](Assignments/03-APIs.md) |
| 7 | Thu, Dec  7 | [Module 5: Databases](Assignments/04-Databases.md) |

5. [Pymongo Todo List](Assignments/module-5-tutorial.md)

## Learning Modules

This course has been broken down into 5 modules for students to approach at their own pace. See the **schedule** below for recommendations on where you should be at in terms of content completion to help assess your pace.

### Although this course has self-pacing elements--attendance is still a requirement! We will be doing activites, checking-in, and learning as a class!

#### MODULE 1: [ Introduction to internet communication patterns, C.R.U.D, and servers](https://handsome-air-ad0.notion.site/MODULE-1-Intro-to-Flask-Forms-54dd4bdc06494f6f9fd44e73ae5fd907) 

1. [Introduction to the Request/Response Cycle](https://handsome-air-ad0.notion.site/Introduction-to-the-Request-Response-Cycle-3458f6f619bd4e84b79f01a8731e6818)
2. [Setting up and Using Flask Servers](https://handsome-air-ad0.notion.site/Setting-up-and-Using-Flask-Servers-757e541158ed4eefa71ebd350462bb8b)
3. [Introduction to C.R.U.D](https://handsome-air-ad0.notion.site/Introduction-to-C-R-U-D-7de1dc81889e46f7a0c9220515276923)
4. [`GET` vs `POST`](https://handsome-air-ad0.notion.site/GET-vs-POST-1537f91a237b46f69fd0f0cf5eef66e3)
5. [Working with Route Variables and Forms](https://handsome-air-ad0.notion.site/Working-with-Route-Variables-and-Forms-b96cb82e882d43f580cef4dcf2ccda03)
6. [Interacting with Form Data in Flask](https://handsome-air-ad0.notion.site/Interacting-with-Form-Data-in-Flask-954d1021433e460a8f17abee94fbe9c1)
7. [Understanding `**args` and `**kwargs`](https://handsome-air-ad0.notion.site/Understanding-args-and-kwargs-b677fabf03d44b38952fde75f39efdd5)

#### MODULE 2: [ Creating scalable web applications and templating](https://www.notion.so/makeschool/MODULE-2-Creating-scalable-web-applications-and-templating-f952b99874f44ed7a886609ec4ecbd6c)

1. [Templating](https://www.notion.so/makeschool/Templating-3d4e522e057643169a3af209bea33b77)
2. [Named Parameters](https://www.notion.so/makeschool/Named-Parameters-e86280fd4a7a488eb9494a7de93288a2)
3. [Conditional Rendering with Templates](https://www.notion.so/makeschool/Conditional-Rendering-with-Templates-1d02a420605b4ecc9e999e9f9acdd03d)
4. [Loops in Templates](https://www.notion.so/makeschool/Loops-in-Templates-0350470fb2d349f29fe2af77546e5dd0)
5. [Creating Reusable Components via Template Inheritance](https://www.notion.so/makeschool/Creating-Reusable-Components-via-Template-Inheritance-816309fd9b084509a183a05ca22b4c79)


#### MODULE 3: [ Building robust services that connect to platforms via API's ](https://www.notion.so/makeschool/MODULE-3-Building-robust-services-that-connect-to-platforms-via-API-s-886ab4e636574ebca8e6e157ee8bf82b)
1. [Introduction to APIs](https://www.notion.so/makeschool/Introduction-to-APIs-cb1db95de4c24fdfbbdf9be49d4c201e)
2. [C.R.U.D in API's](https://www.notion.so/makeschool/C-R-U-D-in-API-s-d0478a7c928946b881fa62af058b22cb)
3. [Working with JSON Objects](https://www.notion.so/makeschool/Working-with-JSON-Objects-f95e153725f042a69bd06224f116d8b2)
4. [Testing API Routes with Postman](https://www.notion.so/makeschool/Testing-API-Routes-with-Postman-2c3abe212a424d3682bd94fc3724e180)
5. [Using the Requests Library to Generate User Requests](https://www.notion.so/makeschool/Using-the-Requests-Library-to-Generate-User-Requests-3c5c50b0fc374eb88708bb312a9a1def) - Note! When following the example here you will need to run your server (main.py) in one terminal window and run the firstrequest.py example in a second terminal! 


#### MODULE 4: [ Developing secure and distributable web applications](https://www.notion.so/makeschool/MODULE-4-Developing-secure-and-distributable-web-applications-bcc343ed1483406e8bb928ebf223e19c)
1. [Working with Virtual Environments and the `requirements.txt` File](https://www.notion.so/makeschool/Working-with-Virtual-Environments-and-the-requirements-txt-File-6dc8b6d6b8924d8db65db60eec68dfcc)
2. [Creating and Managing Environment Variables with `dotenv`](https://www.notion.so/makeschool/Creating-and-Managing-Environment-Variables-with-dotenv-ddb6aa5630fe464c884cfc1a75af9c2f)
3. [Leveraging the Datetime Library](https://www.notion.so/makeschool/Leveraging-the-Datetime-Library-c02959f8f3cc45b19e6582c215ed85d0)

#### MODULE 5: [ Introduction to databases and connecting servers to them ](https://www.notion.so/makeschool/MODULE-5-Introduction-to-databases-and-connecting-servers-to-them-ec864dcc497e44339ebb35381eb325a3)
1. [Introduction to Databases](https://www.notion.so/makeschool/Introduction-to-Databases-601c42c9732e46d595dd2c65a4186253)
2. [SQL vs NoSQL and Introduction to MongoDB](https://www.notion.so/makeschool/SQL-vs-NoSQL-and-Introduction-to-MongoDB-782a225705ad418d8c1af422c9c57083)
3. [Connecting a Flask Server to MongoDB Cluster](https://www.notion.so/makeschool/Connecting-a-Flask-Server-to-MongoDB-Cluster-6385c238c38f433f9babc5e85fb67082)
4. [Performing C.R.U.D Operations with PyMongo](https://www.notion.so/makeschool/Performing-C-R-U-D-Operations-with-PyMongo-0689895c65b24873b429423f14bacfa9)
5. [Pymongo Todo List](Assignments/module-5-tutorial.md)



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
