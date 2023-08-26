---
layout: page
released: true
title: ""
---

## Schedule of Topics
{% assign readings = site.cs195_readings | sort: 'date' %}

| Date  | Lecture | Topic                                 | Slides | Readings |
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
  {%- endif %}
{% endfor %}

## Essays

See the [Syllabus](syllabus) for essay grading details. All deadlines are {{site.assignment_time}} Pacific.

{% assign assignments = site.pages | where_exp: "a", "a.path contains 'assignments/' and a.is_h195 == false" %}
{% assign assignments = assignments | sort: 'index' %}

| Essay | Essay Due           | Peer Reviews Due    | Assignment<br/>Specification |
|-------|--------------------|---------------------|---------------------| ---- |
{% for a in assignments -%}
  | {{a.index}} | {{ a.date.due | date: "%a %m/%d" }} |
  {%- if a.has.peer -%}
    {{ a.date.peer | date: "%a %m/%d" }}
  {%- endif -%}
  |
  {%- if a.released -%}
    [link]({{ a.url }})
  {%- else -%}
    link
  {%- endif -%}
  |
{% endfor %}

## Readings and Weekly Surveys

See the [Syllabus](syllabus) for grading details on readings and weekly surveys.
"Required" readings should be done before class for the discussion to make sense. "Recommended" readings will be used as sources in lecture, but we won't assume you've read them.


{% for r in readings reversed %}
  {%- if r.readings_released -%}
    <hr>
    {{- r -}}
  {%- endif %}
{% endfor %}
