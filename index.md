---
layout: page
title: Start
tagline: Supporting tagline
---
{% include JB/setup %}

Welcome! :) 

I will use this place as a way to store some tutorials so I don't lose them. Maybe some of this can be helpful to you. Sometimes I also write about learning and other personal development stuff. At last, but not least, I will practice my writing in english.

I'm also interested in computer vision, C++ development, quantum computing and science in general. 

## List of posts

<ul class="posts">  
	{% for post in site.posts limit:20 %}  
	   <li>  
		   <span>{{ post.date | date_to_string }}</span> &raquo;  
		   <a href="{{ BASE_PATH }}{{ post.url }}">  
		   {{ post.title }}</a>  
	   </li>  
	{% endfor %}  
</ul>

