---
layout: default
title: Grimoire
---

<div>
    <h1 class="MainTitle">The Grimoire</h1>
    <img src="{{ site.baseurl }}assets/images/DiamondOrange.png" width="100%"/>
</div>
<div>
	{% for grimoirePage in site.grimoire %}
	<br/>
	<br/>
	 <ul>
	 	<h2><a href="{{ site.baseurl }}grimoire/{{grimoirePage.slug}}" class="{% if page.url contains grimoirePage.slug %}current{% endif %}">{{ grimoirePage.title }}</a></h2>
	 </ul>	
	 {% endfor %}
</div>