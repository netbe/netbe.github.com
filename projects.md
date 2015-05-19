---
layout: page
title: Projects
permalink: /projects/
---

{% for repository in site.github.public_repositories %}
  {% if repository.type == "owner" %}
    * [{{ repository.name }}]({{ repository.html_url }}) : repository.description
  {% endif %}
{% endfor %}

