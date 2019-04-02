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
	 <ul>
	 	<li><a href="{{ site.baseurl }}grimoire/{{grimoirePage.slug}}" class="{% if page.url contains grimoirePage.slug %}current{% endif %}">{{ grimoirePage.title }}</a></li>
	 </ul>	
	 {% endfor %}
</div>