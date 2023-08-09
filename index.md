---
layout: page
released: true
title: ""
---

**The website for Fall 2023 is under development. Material on these pages may be out of date.**

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

See the [Syllabus](syllabus) for essay grading details.

| Essay | Proposal Due | Essay Due           | Peer Reviews Due    | Assignment<br/>Specification |
|-------|--------------------|---------------------|---------------------| ---- |
| 1     | Wed. 02/15, 11:59pm | Tue. 02/21, 11:59pm | Wed. 03/01, 11:59pm  | TBD |
| 2     | Wed. 03/22, 11:59pm | Tue. 04/04, 11:59pm  | Wed. 04/12, 11:59pm  | TBD |
| Computing<br/>in the News | | Tue. 04/25 11:59pm | Wed. 05/03 11:59 PM | TBD |

## Readings and Weekly Surveys

Readings are "required", "recommended", or "extra". Required readings should be
done before class for the discussion to make sense. Recommended readings will be
used as sources in lecture, but we won't assume you've read them.

See the [Syllabus](syllabus) for grading details on readings and weekly surveys.

{% for r in readings reversed %}
  {%- if r.readings_released -%}
    <hr>
    {{- r -}}
  {%- endif %}
{% endfor %}
