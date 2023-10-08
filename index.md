---
title: Syllabus
layout: default
permalink: /
---

# CHE155: Scientific Programming for Chemistry

## Fall 2023

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

*Important note:* Heejune Park (your TA) is scheduling a tutorial session for Python basics that will take place in Chemistry Annex 4440 from October 4th through 6th, from 5:30 PM to 6:30 PM. The tutorial will use materials adapted from the [Python Intensive Training course](https://ucdavisdatalab.github.io/python_intensive_training/chapters/index.html) given to incoming graduate students. If you are new to Python or need a refresher, you should definitely plan on attending!

Please see the [Installation]({{ "installation" | relative_url }}) page for instructions on setting up the Python environment needed for this course.

## Schedule
{% assign week_list = site.weeks | sort: "w","first" %}

| Week(s) | Topics |
| --- | --- |
{% for week in week_list %}| {{week.week}} | [{{week.pagetitle}}]({{ week.url | relative_url }}) |
{% endfor %}

## Course Organization
![organization]({{ site.baseurl }}/assets/images/organization.png){: width="450"}

The course resources are organized roughly according to this graphic. 
This course has a [Canvas page](https://canvas.ucdavis.edu/courses/802399) that you need your UC Davis login to access.
Course announcements, exercises and projects, and other time-sensitive information will be posted here.
There is also a link to a forum using Piazza which is the preferred way to ask course-related questions.

The course website - the site you're currently on - contains most of the educational contents of the course.
There is a set of detailed installation instructions that guides you through installing the software that will be required to do the assignments on your computer.
The material is divided into ten weeks, and each week has a reading accessible through the links at the top bar.
At the bottom of each reading, there are links to 1-3 interactive Jupyter notebooks containing further reading and interactive code cells.
(In some weeks, the notebooks contain more content than the reading itself).
Note that this website doesn't contain information about the assignments because Canvas is better suited to posting time-sensitive material.

The [GitHub repository](https://github.com/leeping/che155) for the course hosts the Jupyter notebook files as well as the source files for the course website. 
You usually don't need to visit this site as it's mainly for administrative purposes; however, if any links to files from the course website are broken, you can find them here.

## Course Expectations and Grading

It is expected that students will regularly attend the class sessions and participate in the discussion. In addition, for this class the instructional notebooks are available on the course website, and students should explore these notebooks before class, follow along with the code during class, and ask questions about any code that is unclear.

Grading in the course will be primarily based on 8 assignments, including a final project due during finals week. The assignments that are designated as "Projects" are worth more points, and may be worked on individually or, with permission, in small groups of up to 3 people. All members of a group are expected to contribute equally. Failure to adequately contribute to a group project could result in a grade penalty and forfeiting the privilege to work in groups on future projects.

Assignments are generally due at the end of the week.  The current schedule of assignments is as follows (subject to change):

- Week 1: Working with numbers and strings (the first day of class falls on "Week 0".)
- Week 2: Creating a grade histogram with Matplotlib
- Week 3: Creating a molecular orbital diagram
- Week 5: Least squares fitting of kinetic model
- Week 6: Spectral processing pipeline using Fast Fourier Transforms (*Project*)
- Week 7: Introduction to RDKit
- Week 9: Cheminformatics and Quantum Chemistry (*Project*)
- Finals Week: Building a Force Field (*Project*)
