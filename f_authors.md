---
layout: page
title: Authors
permalink: /authors/
---

<ul class="tags-box">
	{% if site.posts != empty %}
	{% for author in site.authors %}
	<a href="#{{ author[0] }}" title="{{ author[1].name }}">{{ author[1].name }}</a> &nbsp;
	{% endfor %}
</ul>

{% capture rawauthors %}{% for post in site.posts %}{% if post.author %}{{ post.author }}|{% endif %}{% endfor %}{% endcapture %}
{% assign authors = rawauthors | split:'|' | sort %}

<ul class="tags-box">
	{% for author in site.authors %}
                {% assign posts = (site.posts | where: "author" , author[0]) %}
		<li  id="{{ author[0] }}">{{ author[0] }} &mdash; {{ author[1].name }}</li>
		{% for post in posts %}
			<time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time> &raquo;
			<a href="{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a><br />
		{% endfor %}
	{% endfor %}
</ul>
{% else %}
	<span>No posts</span>
{% endif %}


