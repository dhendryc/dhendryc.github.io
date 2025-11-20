---
layout: cv
permalink: /talks/
title: talks & activities
description: Conference and seminar talks, as well as conferences and workshops attended.
nav: true
nav_order: 3
---

<!-- _pages/talks.md -->

<div class="talks">
  {% for entry in site.data.talks %}
    <a class="anchor" id="{{ entry.title }}"></a>
    <div class="card mt-3 p-3">
      <h3 class="card-title font-weight-medium">{{ entry.title }}</h3>
      <div>
        {% if entry.type == 'list' %}
          {% include cv/list.liquid %}
        {% elsif entry.type == 'map' %}
          {% include cv/map.liquid %}
        {% elsif entry.type == 'nested_list' %}
          {% include cv/nested_list.liquid %}
        {% elsif entry.type == 'time_table' %}
          {% include cv/time_table.liquid %}
        {% elsif entry.type == 'list_groups' %}
          {% include cv/list_groups.liquid %}
        {% else %}
          {{ entry.contents }}
        {% endif %}
      </div>
    </div>
  {% endfor %}
</div>

