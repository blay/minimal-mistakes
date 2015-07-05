---
layout: page
permalink: research.html
title:
image:
 feature: knoll_narrow.jpg
 credit: Tom Sachs
---

#### Academic Research

<div class="tiles">
{% for post in site.categories.academic limit:5 %}
{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->

#### Internet and Hacking

<div class="tiles">
{% for post in site.categories.internet limit:5 %}
{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->

#### Art and Code

<div class="tiles">
{% for post in site.categories.art limit:5 %}
{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
