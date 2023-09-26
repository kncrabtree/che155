---
title: Syllabus
layout: default
permalink: /
---

# CHE155: Scientific Programming for Chemistry

## Fall 2022

- Instructor: [Lee-Ping Wang](mailto:leeping@ucdavis.edu)
- Class Info: MWF 3:10-4:00 PM, Giedt 1006
- Office Hours: W 4:10-5:00 PM, Chemistry 190B
- TA: [Heejune Park](mailto:heepark@ucdavis.edu)
- TA Office Hours: TBA
- [CHE 155 Github Repository](https://github.com/leeping/che155)

## Course Overview and Objectives

Programming has become an essential tool for scientists. In chemistry, computer programs are used to calculate molecular properties, simulate chemical processes in complex environments, acquire data from instruments, and analyze data. The goal of this course is to equip students with basic scientific programming skills in [Python](https://www.python.org) with an emphasis on applications in chemistry. Python is a widely used, general-purpose scripting language with extensive libraries for scientific computing. By the end of the course, students should be able to:

- Visualize 1D, 2D, and 3D data using Matplotlib
- Efficiently perform vectorized computations using arrays
- Analyze and manipulate large data sets using
- Fit experimental data to nonlinear model functions
- Numerically integrate functions and differential equations
- Read, write, and process molecular structures with standard chemical file formats
- Set up and run basic electronic structure and molecular dynamics calculations
- Create machine learning models for fitting nonlinear data

**This course includes an introduction to Python programming for those with no prior experience, but it does not fully replace a formal programming course such as ECS 032A.** You are expected to learn the basics of Python by supplementing the tutorial with outside learning. For best results you are encouraged to take a programming course prior to, or concurrently with this one. I also recommend learning Python basics from outside reading such as Chapters 1-11 of [Automate the Boring Stuff](https://automatetheboringstuff.com/).

*Important note:* Heejune Park (your TA) is scheduling a tutorial session for Python basics that will take place sometime in the first two weeks of class outside of normal hours. The tutorial will use materials adapted from the [Python Intensive Training course](https://ucdavisdatalab.github.io/python_intensive_training/chapters/index.html) given to incoming graduate students.  If you are new to Python or need a refresher, you should definitely plan on attending!

Please see the [Installation]({{ "installation" | relative_url }}) page for instructions on setting up the Python environment needed for this course.

## Schedule
{% assign week_list = site.weeks | sort: "w","first" %}

| Week(s) | Topics |
| --- | --- |
{% for week in week_list %}| {{week.week}} | [{{week.pagetitle}}]({{ week.url | relative_url }}) |
{% endfor %}

## Course Expectations and Grading

It is expected that students will regularly attend the class sessions and participate in the discussion. In addition, for this class the instructional notebooks are available on the course website, and students should explore these notebooks before class, follow along with the code during class, and ask questions about any code that is unclear.

Grading in the course will be primarily based on 4 coding projects: 3 during the quarter and a final project due during finals week. Projects may be worked on individually or, with permission, in small groups of up to 3 people. However, if working in groups, you may not work with the same person on more than 2 projects. All members of a group are expected to contribute equally. Failure to adequately contribute to a group project could result in a grade penalty and forfeiting the privilege to work in groups on future projects.
These 4 projects will be worth at least 80% of the course grade.

Up to 20% of the grade will be based on short coding exercises that can be completed quickly.
The number of these will be determined as the course proceeds, but there will be no more than 1 brief exercise per week, and they will count equally toward the course grade.
