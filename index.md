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
   <hr style="width:0px"/>
  <section opacity="0">
    <blockquote>
        <h2>Chris Scholl</h2>
        <em>Medium human, neutral good</em>
        <hr/>
        <ul>
            <dl><strong>Armor Class</strong> 10</dl>
            <dl><strong>Hit Points</strong> 22(4d8 + 4)</dl>
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
                    <td style="text-align:center">12 (+1)</td>
                    <td style="text-align:center">12 (+1)</td>
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
        <p><strong><em>I'll learn what you know.</em></strong> "Chris Scholl is eager to learn and share knowledge with fellow creatures, whether through declaration, demonstration, or documentation."</p>
        <p><strong><em>Says it well.</em></strong> "Chris Scholl has advantage when communicating with teammates"</p>
        <p><strong><em>Focused.</em></strong> "Man, I lost track of time. But this widget I made is pretty cool!"</p>
        <h3 id="actions">Actions</h3>
        <p><strong><em>Accidentally step on toes.</em></strong> <em>Melee Weapon Attack:</em> +0 to hit, reach 5ft., one target. <em>Hit</em> 5 (1d10 + 0) </p>
    </blockquote>
</section>
<h3>About Me</h3>
<p>
  I am a multi-classed Software Engineer with two levels of Data Analyst. I work with React, Redux, and various JavaScript libraries to build client-facing applications. I have used ABBYY tools to build and test layouts for OCR capture of insurance documents using conditional logic, and I have some domain knowledge around property and casualty insurance products. I would love to work for a company that seeks to enrich humans and make a positive impact in the world.
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
