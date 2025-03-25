---
title: Syllabus
layout: default
permalink: /
---

# CHE155: Scientific Programming for Chemistry

## Spring 2025

- Instructor: [{{ site.instructor }}](mailto:{{ site.email }})
- Class Info: MWF 10:00-10:50 AM, Wellman 203
- Office Hours: T 12:00-1:00 PM, F 4:00-5:00 PM, Chemistry 2206
- [CHE 155 Github Repository]({{ site.github_url }})

## Course Overview and Objectives

Programming has become an essential tool for scientists. In chemistry, computer programs are used to calculate molecular properties, simulate chemical processes in complex environments, acquire data from instruments, and analyze data. The goal of this course is to equip students with basic scientific programming skills in [Python](https://www.python.org) with an emphasis on applications in chemistry. Python is a widely used, general-purpose scripting language with extensive libraries for scientific computing. By the end of the course, students should be able to:

- Visualize 1D, 2D, and 3D data using Matplotlib
- Efficiently perform vectorized computations using arrays
- Perform statistical analyses on large data sets
- Fit experimental data to nonlinear model functions
- Numerically integrate functions and differential equations
- Carry out signal processing and filtering with fast Fourier transforms
- Read, write, and process molecular structures with standard chemical file formats
- Set up and run basic electronic structure and molecular dynamics calculations
- Create machine learning models for fitting nonlinear data

**This course includes an introduction to Python programming for those with no prior experience, but it does not fully replace a formal programming course such as ECS 032A.** You are expected to learn the basics of Python by supplementing the tutorial with outside learning. For best results you are encouraged to take a programming course prior to, or concurrently with this one. I also recommend learning Python basics from outside reading such as Chapters 1-11 of [Automate the Boring Stuff](https://automatetheboringstuff.com/).

Please see the [Installation]({{ "installation" | relative_url }}) page for instructions on setting up the Python environment needed for this course.

## Schedule
{% assign week_list = site.weeks | sort: "w","first" %}

| Week(s) | Topics |
| --- | --- |
{% for week in week_list %}| {{week.week}} | [{{week.pagetitle}}]({{ week.url | relative_url }}) |
{% endfor %}

## Course Organization
![organization]({{ site.baseurl }}/assets/images/organization-{{ site.github_username }}.png){: width="450"}

The course resources are organized roughly according to this graphic. 
This course has a [Canvas page](https://canvas.ucdavis.edu/courses/{{ site.canvasid }}) that you need your UC Davis login to access.
Course announcements, exercises and projects, and other time-sensitive information will be posted here.
There is also a link to the class Discord server which is the preferred way to ask course-related questions.

The course website - the site you're currently on - contains most of the educational content of the course.
There is a set of detailed installation instructions that guides you through installing the software that will be required to do the assignments on your computer.
The material is divided into ten weeks, and each week has a reading accessible through the links at the top bar.
At the bottom of each reading, there are links to 1-3 interactive Jupyter notebooks containing further reading and interactive code cells.
(In some weeks, the notebooks contain more content than the reading itself).
Note that this website does not contain information about the assignments because Canvas is better suited to posting time-sensitive material.

The [GitHub repository]({{ site.github_url }}) for the course hosts the Jupyter notebook files as well as the source files for the course website. 
You usually don't need to visit this site as it's mainly for administrative purposes; however, if any links to files from the course website are broken, you can find them here.

## Course Expectations and Grading

It is expected that students will regularly attend the class sessions and participate in the discussion. Instructional notebooks are available on the course website, and students should explore these notebooks before class, follow along with the code during class, and ask questions about any code that is unclear.

Grading in the course will be primarily based on several coding projects. Details of the projects and their due dates will be posted on Canvas. Projects may be worked on individually or, with permission, in small groups of up to 3 people. However, if working in groups, you may not work with the same person on more than 1 project: your group must be different each time. All members of a group are expected to contribute equally. Failure to adequately contribute to a group project could result in a grade penalty and forfeiting the privilege to work in groups on future projects. These projects will be worth at least 75% of the course grade.

Up to 25% of the grade will be based on participation in short coding exercises that can be completed quickly, and these will be assigned in class on Fridays at which attendance will be required.
