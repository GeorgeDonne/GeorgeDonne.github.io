---
# change layout from 'page' to 'gd-dark'
layout     : gd-dark
title      : About Me -- George Donne
gd-example : An gd-example value here
---

<!-- 
site.title : 'title' in _config.yml
site.author.name : name of author, defined in _config.yml
page.gd-example : gd-example defined in front matter.
-->

This page describes the amazing "{{ site.title }} " by " {{ site.author.name }}."
{{ page.gd-example }}


The following is a picture of tiger.
{% include big-cat.html %}

Some Markdown content describing your site.


## About About Pages

The About page is a common convention found on websites.
It is your opportunity to let us know all the details "about" your project:

- focus and topic area
- people involved
- code and projects used
- and something else -- from George Donne

## List of Animals

{% for animal in site.data.animals %}
- The {{ animal.name }} is a {{ animal.size }} animal.
{% endfor %}

## Large Animals are Better

{% for animal in site.data.animals %}
{% if animal.size == "large" %}- <strong style="color: {{ animal.color }};">{{ animal.name }}</strong>
{% else %}- <small>{{ animal.name }}</small>
{% endif %}
{% endfor %}

## List of Small Animals

{% assign small_animals = site.data.animals | where: "size", "small" %}
{% for animal in small_animals %}
- {{ animal.name | upcase }}
{% endfor %}
