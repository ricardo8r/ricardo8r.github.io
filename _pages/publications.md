---
layout: archive
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar</a>.</u>
{% endif %}
{% if author.researchgate %}
or <u><a href="{{author.researchgate}}">my ResearchGate</a>.</u>
{% endif %}
{% include base_path %}

## Preprints & in preparation

{% for post in site.publications reversed %}
  {% if post.pubsource == "arXiv" %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

## Peer-Reviewed Journal Publications

{% for post in site.publications reversed %}
  {% if post.pubsource == "journal" %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}
