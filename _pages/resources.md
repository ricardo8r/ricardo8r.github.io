---
layout: archive
title: "Resources"
permalink: /resources/
author_profile: true
---

{% include base_path %}

Most of my work right now happens on python and [FEniCS](https://fenicsproject.org/).
Here are some other codes and packages that I use.
{% for post in site.resources%}
  {% include archive-resource.html %}
{% endfor %}
