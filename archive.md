---
layout: post-index
permalink: archive.html
title: All Posts
excerpt: "A List of Posts"
---

<div id="index">
<h1>{{ page.title }}</h1>

<h4><div class="foo" style="background-color:#FFFF88;float: left;width: 20px;height: 20px;margin: 5px;margin-top:0px;border-width: 1px;border-style: solid;border-color: rgba(0,0,0,.2);"></div><a href="tldr.html"> Long Posts.</a></h4>

<h4><div class="foo" style="background-color:#E3E2E1;float: left;width: 20px;height: 20px;margin: 5px;margin-top:0px;border-width: 1px;border-style: solid;border-color: rgba(0,0,0,.2);"></div> <a href="meta.html"> Meta Posts.</a></h4>

<h4><div class="foo" style="background-color:#E6E8FC;float: left;width: 20px;height: 20px;margin: 5px;margin-top:0px;border-width: 1px;border-style: solid;border-color: rgba(0,0,0,.2);"></div><a href="english.html"> English.</a></h4>


{% for post in site.posts  %}
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
<h2 class="link-post"><a href="{{ post.url | remove_first:'/'}}" title="{{ post.title }}">{{ post.title }}</a> <a href="{{ post.link }}" target="_blank" title="{{ post.title }}"><i class="fa fa-link"></i></a></h2>
{% elsif  post.tags contains 'secret' %}
<h2>| | | S E C R E T | | |</h2>
{% else %}
{% if post.tags contains 'tldr'  %}
<h2 class="tldr"><a href="{{ post.url | remove_first:'/'}}" title="{{ post.title }}">{{ post.title }}</a></h2>
{% elsif post.tags contains 'meta'  %}
<h2 class="meta"><a href="{{ post.url | remove_first:'/'}}" title="{{ post.title }}">{{ post.title }}</a></h2>
{% elsif post.tags contains 'english'  %}
<h2 class="english"><a href="{{ post.url | remove_first:'/'}}" title="{{ post.title }}">{{ post.title }}</a></h2>
{% else %}
<h2><a href="{{ post.url | remove_first:'/'}}" title="{{ post.title }}">{{ post.title }}</a></h2>
{% endif f%}
{% if post.summary %}
<p>{{ post.summary | strip_html | truncate: 160 }}</p>
{% else %}
<p>{{ post.excerpt | strip_html | truncate: 160 }}</p>
{% endif %}
{% endif %}
</article>
{% endfor %}
</div><!-- /#index -->
