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
- TA: [Zach Buchanan](mailto:zsbuchanan@ucdavis.edu)

## Course Overview and Objectives

Programming has become an essential tool for scientists. In chemistry, computer programs are used to calculate molecular properties, simulate chemical processes in complex environments, acquire data from instruments, and analyze data. The goal of this course is to equip students with basic scientific programming skills in [Python](https://www.python.org) with an emphasis on applications in chemistry. Python is a widely used, general-purpose scripting language with extensive libraries for scientific computing. By the end of the course, students should be able to:

- Use `matplotlib` to visualize 1D, 2D, and 3D data
- Efficiently perform vectorized computations over Numpy arrays
- Fit experimental data to nonlinear model functions
- Numerically integrate functions and differential equations
- Represent molecular structures with standard chemical file formats
- Set up and run basic electronic structure and molecular dynamics calculations

**Students in the course are expected to have prior experience with Python!** The course assumes knowledge topics covered by a typical introductory Python course, such as Chapters 1-11 of [Automate the Boring Stuff](https://automatetheboringstuff.com/).

Please see the [Installation](/installation) page for instructions on setting up the Python environment needed for this course.

## Schedule
{% assign week_list = site.weeks | sort: "w","first" %}

| Week(s) | Topics |
| --- | --- |
{% for week in week_list %}| {{week.week}} | [{{week.pagetitle}}]({{ week.url | relative_url }}) |
{% endfor %}
