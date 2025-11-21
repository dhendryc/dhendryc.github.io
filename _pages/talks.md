---
layout: page
permalink: /talks/
title: Talks & Activities
#description: Conference and seminar talks, as well as conferences and workshops attended.
nav: true
nav_order: 3
title_class: text-center
---

<!-- _pages/talks.md -->

{% assign talks_section = site.data.talks | where: "title", "Talks & Posters" | first %}
{% if talks_section %}
{% assign talks_list = talks_section.contents %}
{% if talks_list and talks_list.size > 0 %}
### Talks and posters
{% for activity in talks_list %}
{% assign type_line = activity.description | first | default: '' | strip_html | strip %}
{% assign cleaned_type = type_line | remove: 'Type:' | strip %}
* {{ activity.year }} • **{{ activity.institution }}**{% if activity.location %}, {{ activity.location }}{% endif %}  
  {% if cleaned_type != '' %}{{ cleaned_type }}{% endif %}{% if activity.linkitems %}
  {% for link in activity.linkitems %} • [[{{ link.linkname | downcase }}]]({{ link.link }}){% endfor %}{% endif %} • *{{ activity.title }}*
{% endfor %}
{% endif %}
{% endif %}

{% assign events_section = site.data.talks | where: "title", "Attended Events" | first %}
{% if events_section %}
{% assign events_list = events_section.contents %}
{% if events_list and events_list.size > 0 %}
### Event participation
{% for activity in events_list %}
* {{ activity.year }} • **{{ activity.title }}**{% if activity.institution %}, {{ activity.institution }}{% endif %}{% if activity.location %}, {{ activity.location }}{% endif %}
{% endfor %}
{% endif %}
{% endif %}

{% assign seminars_section = site.data.talks | where: "title", "Seminar Talks" | first %}
{% if seminars_section %}
{% assign seminars_list = seminars_section.contents %}
{% if seminars_list and seminars_list.size > 0 %}
### Seminar talks
{% for activity in seminars_list %}
* {{ activity.year }} • **{{ activity.institution }}**{% if activity.location %}, {{ activity.location }}{% endif %}  
  {% if activity.linkitems %}
  {% for link in activity.linkitems %}• [[{{ link.linkname | downcase }}]]({{ link.link }}) {% endfor %}{% endif %}*{{ activity.title }}*
{% endfor %}
{% endif %}
{% endif %}

{% assign stays_section = site.data.talks | where: "title", "Research Stays" | first %}
{% if stays_section %}
{% assign stays_list = stays_section.contents %}
{% if stays_list and stays_list.size > 0 %}
### Research stays
{% for stay in stays_list %}
* {{ stay.year }} • **{{ stay.institution }}**{% if stay.location %}, {{ stay.location }}{% endif %}  
  {% if stay.description %}{{ stay.description | join: ' • ' }}{% endif %}
{% endfor %}
{% endif %}
{% endif %}
