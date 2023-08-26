---
layout: page
released: true
title: "CS H195: Honors Social Implications of Computer Technology"
---

Jump on this page:

- CS H195 Syllabus: [link](#cs-h195-syllabus)
- Projects: [link](#projects)
- CS H195 Weekly Readings and Journal Entries: [link](#cs-h195-readings-and-journal-entries)

{% assign readings = site.csH195_discussions | sort: 'date' %}

| Date  | Discussion | Topic                                 | Slides | Readings |
|-------|-------- | --------------------------------------|--------| ----------- |
{% for r in readings -%}
  | {{ r.date | date: "%m/%d" }} | {{ r.number }} | {{ r.title }} |
  {%- if r.slides.released -%}
    [link]({{ r.slides.link }})
  {%- else -%}
    link
  {%- endif -%}
  |
  {%- if r.readings_released -%}
    [jump](#lecture{{ r.number }})
  {%- else -%}
    jump
  {%- endif -%}
  |
{% endfor %}

## Projects

{% assign assignments = site.pages | where_exp: "a", "a.path contains 'assignments/' and a.is_h195 == true" %}
{% assign assignments = assignments | sort: 'index' %}

|  | Project  | Project<br/>Released | Project<br/>Due | Assignment<br/>Specification |
| ----- | ------ | ----- | --- | --- |
{% for a in assignments -%}
  | {{a.short_title}} | {{a.title}} | {{a.date.release | date: "%a %m/%d"}} | {{ a.date.due | date: "%a %m/%d" }} |
  {%- if a.released -%}
    [link]({{ a.url }})
  {%- else -%}
    link
  {%- endif -%}
  |
{% endfor %}

***

## CS H195 Syllabus

### Course components

**To pass this course, you must:**

- Attend most <b>CS 195 lectures</b>,
- Be present at all <b>CS H195 discussions</b>,
- Complete all <b>CS 195/H195 readings</b> and <b>CS 195 surveys</b>,
- Keep your <b>QQC journal</b> up-to-date with <b>all CS 195/H195 readings and H195 additional journal entries</b>, and
- Complete passing work on all <b>CS H195 projects</b>.

**QQC Document**: QQC for CS H195 is different from QQC for CS 195. We have time for discussing the readings in section, so instead of posting on Ed you will jot down notes about your readings in a running QQC document to prepare for class discussion. See the QQC document page for more details.

**Grading Policy**: 
We understand things come up during the semester and
synchronous participation may not always be possible. This course is P/NP, and
we will make every effort to work with you to help you pass this course.

CS 195 lecture attendance and CS195 survey completion will be graded according to [CS195 course policies](syllabus). Attendance is expected at every CS H195 discussion. If you need to miss any, we'd appreciate early notice so we can assign you make up work.

**Accessing Readings**: You do not need to purchase any books for this course; most are available either openly or via the library.
To use the online UC Berkeley Library: Visit [https://search.library.berkeley.edu/](https://search.library.berkeley.edu/) and authenticate with CalNet. Then search for <b>online access</b> to the book you are searching for. Alternatively, use the [Library proxy bookmarklet](https://guides.lib.berkeley.edu/ezproxy/browser-bookmarklet), which works well for academic papers.
If access is not available through the Library, then we will provide additional links as needed.

<!--
Intead of the CS 195 essays, this semester we are building new H195 project assignments.
This semester, we are trying some new assignments for CS H195. We appreciate your working with us to design this course, and we welcome your feedback!!

<b>1. Social Media Simulation</b>:
[link](proj1)
(individual)
Analyze the dynamics of
information bubbles and polarization in social network models. Submit a writeup.
<br/>

<b>2. Teaching Computing in the News</b>:
[link](proj2)
What H195 discussion would
you run? Build a lesson plan for a 50-minute discussion for (future) H195
students to engage critically with the social context of a particular computing
technology. We will provide readings on pedagogical practices.


<b>3. Technology and the Community</b>: (groups) Engage with the community to
inform impacts of technology on particular groups of people. This project is
*open-ended* and we are hoping that we can co-design this assessment with
you. What do you want to have learned from this class? What kind of community
do you want to participate in?
  -->

***

## CS H195 Readings and Journal Entries

{% for r in readings reversed %}
  {%- if r.readings_released -%}
    {{- r -}}
    <hr>
  {%- endif %}
{% endfor %}
