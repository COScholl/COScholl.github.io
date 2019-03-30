---
layout: default
title: Home
---
<div>
  <div>
    <h1 class="MainTitle">The Adventure Starts Here</h1>
    <img src="assets/images/DiamondOrange.png" width="100%"/>
  </div>
  <hr/>
  <p>
    Welcome, adventurers! This website is the springboard for 
    all of my creative endeavors in the realms of software engineering
    and roleplaying game design.
  </p>
  <p>
    It is my goal to post code snippets in the <strong>Grimoire</strong> section,
    to post creature designs and other role-playing game content in the 
    <strong>Role-Playing Games</strong> section, and to add more specialized 
    content as my career evolves.
  </p>
  <p>
    Expect this page to change over time, and get to know about 
    my motivations by clicking the <strong>About</strong> link in the sidebar nav!
  </p>
  <div markdown="1" class="stats">
   <hr/>
<section>
    <blockquote>
        <h2>Chris Scholl</h2>
        <em>Medium human, neutral good</em>
        <hr/>
        <ul>
            <dl><strong>Armor Class</strong> 10</dl>
            <dl><strong>Hit Points</strong> 9(2d8)</dl>
            <dl><strong>Speed</strong> 30 feet</dl>
        </ul>
        <hr/>
        <table>
            <thead>
                <tr>
                    <th style="text-align:center">STR</th>
                    <th style="text-align:center">DEX</th>
                    <th style="text-align:center">CON</th>
                    <th style="text-align:center">INT</th>
                    <th style="text-align:center">WIS</th>
                    <th style="text-align:center">CHA</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td style="text-align:center">10 (+0)</td>
                    <td style="text-align:center">10 (+0)</td>
                    <td style="text-align:center">10 (+0)</td>
                    <td style="text-align:center">10 (+0)</td>
                    <td style="text-align:center">10 (+0)</td>
                    <td style="text-align:center">10 (+0)</td>
                </tr>
            </tbody>
        </table>
        <hr/>
        <ul>
            <strong>Senses</strong> hindsight 20/20, passive Perception 10
        </ul>
        <ul>
            <strong>Languages</strong> English, Spanish
        </ul>
        <ul>
            <strong>Challenge</strong> 1/4 (50 XP)
        </ul>
        <hr/>
        <p><strong><em>Way Too Intense.</em></strong> "No, I'm not upset. I'm just thinking about something. Seriously."</p>
        <h3 id="actions">Actions</h3>
        <p><strong><em>Step on toes.</em></strong> <em>Melee Weapon Attack:</em> +0 to hit, reach 5ft., one target. <em>Hit</em> 5 (1d10 + 0) </p>
    </blockquote>
</section>
<h3>About Me</h3>
<p>
  I am currently a Junior Data Analyst for Groundspeed Analytics, Inc. I am working on multi-classing as Junior Developer with
  a focus on front-end development.
</p>
  </div>
</div>
<!--
<div class="posts">
  {% for post in paginator.posts %}
  <div class="post">
    <h1 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h1>

    <span class="post-date">{{ post.date | date_to_string }}</span>

    {{ post.content }}
  </div>
  {% endfor %}
</div>

<div class="pagination">
  {% if paginator.next_page %}
    <a class="pagination-item older" href="{{ site.baseurl }}page{{paginator.next_page}}">Older</a>
  {% else %}
    <span class="pagination-item older">Older</span>
  {% endif %}
  {% if paginator.previous_page %}
    {% if paginator.page == 2 %}
      <a class="pagination-item newer" href="{{ site.baseurl }}">Newer</a>
    {% else %}
      <a class="pagination-item newer" href="{{ site.baseurl }}page{{paginator.previous_page}}">Newer</a>
    {% endif %}
  {% else %}
    <span class="pagination-item newer">Newer</span>
  {% endif %}
</div>
-->

