---
layout: archive
title: "Resources"
permalink: /resources/
author_profile: true
---

{% include base_path %}

Here I include some of the codes and other resources that I use.
{% for post in site.resources%}
  {% include archive-resource.html %}
{% endfor %}
