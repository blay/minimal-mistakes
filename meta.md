---
layout: post-index
permalink: txt.html
title: Texts about Writing
excerpt: "A collection of texts about writing texts"
---

<div id="index">
<h1>{{ page.title }}</h1>
<h2>{{ page.excerpt }}</h2>


{% for post in site.tags.txt %}
{% unless post.next %}
<h3>{{ post.date | date: '%Y' }}</h3>
{% else %}
{% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
{% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
{% if year != nyear %}
<h3>{{ post.date | date: '%Y' }}</h3>
{% endif %}
{% endunless %}
<article>
{% if post.link %}
<h2 class="link-post"><a href="{{ post.url | remove_first:'/'}}" title="{{ post.title }}">{{ post.title }}</a> <a href="{{ post.link }}" target="_blank" title="{{ post.title }}"><i class="fa fa-link"></i></h2>
{% else %}
<h2><a href="{{ post.url | remove_first:'/'}}" title="{{ post.title }}">{{ post.title }}</a></h2>
{% if post.summary %}
<p>{{ post.summary | strip_html | truncate: 160 }}</p>
{% else %}
<p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
{% endif %}
{% endif %}
</article>
{% endfor %}
</div><!-- /#index -->