---
layout: page
date: 2013-12-12 00:00:00 +0530
title: Travelogue
permalink: /category/travelogue/
---

<div class="post">
	<span><a href="{{ site.url }}">home</a>&nbsp;&gt;&nbsp;<a href="{{ site.url }}/categories">categories</a></span>
  	
    {% for post in site.categories.travelogue %}

    	{% if forloop.index == 0 %}
    		{% assign prev_month = "none" %}
    	{% endif %}

		{% capture current_month %}{{ post.date | date: '%B' }}{% endcapture %}

		{% if prev_month != current_month %}		
			<h3>{{ post.date | date: '%B, %Y' }}</h3>
		{% endif %}	

		<p>&#149;&nbsp;&nbsp;<a href="{{ post.url }}">{{ post.title }}</a></p>
		{% assign prev_month = current_month %}

    {% endfor %}
	
</div>