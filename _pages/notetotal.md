---
layout: archive
permalink: /notetotal/
title: "笔记整理"
author_profile: true
---

{% include toc %}

{% capture written_year %}'None'{% endcapture %}
{% for post in site.notes %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
<h2 id="{{ year | slugify }}" class="archive__subtitle"></h2>
# {{ year }}
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}
{% endfor %}