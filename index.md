---
title: Syllabus
layout: default
permalink: /
---

# CHE155: Scientific Programming for Chemistry

## Spring 2021

- Instructor: [Kyle N. Crabtree](mailto:kncrabtree@ucdavis.edu)
- Class Info: MWF 10:00-10:50 am, online (see Canvas for link)
- Office Hours: F 11:00-12:00, online (see Canvas for link)
- TA: [Zach Buchanan](mailto:zsbuchanan@ucdavis.edu) Office hours TBD
- [CHE 155 Github Repository](https://github.com/kncrabtree/che155)

## Course Overview and Objectives

Programming has become an essential tool for scientists. In chemistry, computer programs are used to calculate molecular properties, simulate chemical processes in complex environments, acquire data from instruments, and analyze data. The goal of this course is to equip students with basic scientific programming skills in [Python](https://www.python.org) with an emphasis on applications in chemistry. Python is a widely used, general-purpose scripting language with extensive libraries for scientific computing. By the end of the course, students should be able to:

- Use `matplotlib` to visualize 1D, 2D, and 3D data
- Efficiently perform vectorized computations over Numpy arrays
- Fit experimental data to nonlinear model functions
- Numerically integrate functions and differential equations
- Represent molecular structures with standard chemical file formats
- Set up and run basic electronic structure and molecular dynamics calculations

**Students in the course are expected to have prior experience with Python!** The course assumes knowledge topics covered by a typical introductory Python course, such as Chapters 1-11 of [Automate the Boring Stuff](https://automatetheboringstuff.com/).

Please see the [Installation](/che155/installation) page for instructions on setting up the Python environment needed for this course.

## Schedule
{% assign week_list = site.weeks | sort: "w","first" %}

| Week(s) | Topics |
| --- | --- |
{% for week in week_list %}| {{week.week}} | [{{week.pagetitle}}]({{ week.url | relative_url }}) |
{% endfor %}

## Course Expectations and Grading

It is expected that students will regularly attend the class sessions and participate in the discussion. In addition, for this class the instructional notebooks are available on the course website, and students should explore these notebooks before class, follow along with the code during class, and ask questions about any code that is unclear.

Grading in the course will be primarily based on 4 coding projects: 3 during the quarter and a final project due during finals week. Projects may be worked on individually or, with permission, in small groups of up to 3 people. However, if working in groups, you may not work with the same person on more than 1 project: your group must be different each time. All members of a group are expected to contribute equally. Failure to adequately contribute to a group project could result in a grade penalty and forfeiting the privilege to work in groups on future projects.
These 4 projects will be worth at least 90% of the course grade.

Up to 10% of the grade will be based on short coding exercises that can be completed quickly.
The number of these will be determined as the course proceeds, but there will be no more than 1 brief exercise per week, and they will count equally toward the course grade.
