---
layout: page
title: Tags
---

<h1 class="tags-title">Tags</h1>
<div class="tags-list">
	{% for tag in site.tags %}
		{% capture tag_name %}{{ tag | first }}{% endcapture %}
		<a class="tag-link" href="#{{ tag_name }}">{{ tag_name }}</a>
	{% endfor %}
</div>

<div class="tags-index">
	{% for tag in site.tags %}
		{% capture tag_name %}{{ tag | first }}{% endcapture %}
		<h3>{{ tag_name }}</h3>
		<ul id="{{ tag_name }}">
			{% for post in site.tags[tag_name] %}
				{% include time-to-read.html %}
				<li class="post-short">
		      <a href="{{ site.baseurl | append: post.url }}"><h3>{{ post.title }}</h3></a>
		      <p class="date">{{ post.date | date_to_string }} <span class="reading-time"> - {{ minutesText }}</span></p>
		    </li>
			{% endfor %}
		</ul>
	{% endfor %}
</div>