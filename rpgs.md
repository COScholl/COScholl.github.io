---
layout: default
title: RPGs
---

<div>
    <h1 class="MainTitle">Role Playing Games</h1>
    <img src="{{ site.baseurl }}assets/images/DiamondOrange.png" width="100%"/>
</div>
<div>
	{% for rpg in site.rpgs %}
	 <ul>
	 	<br/>
	 	<br/>
	 	<h2><a href="{{ site.baseurl }}rpgs/{{rpg.slug}}" class="{% if page.url contains rpg.slug %}current{% endif %}">{{ rpg.title }}</a></h2>
	 </ul>	
	 {% endfor %}
</div>