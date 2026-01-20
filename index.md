---
layout: default
---

<div class="grid">
  <aside class="left-col">
    <div class="profile">
      <img class="profile-photo" src="{{ site.data.profile.photo | relative_url }}" alt="Portrait">
      <div class="profile-text">
        <div class="profile-name">{{ site.data.profile.name }}</div>
        <div class="profile-title">{{ site.data.profile.title }}</div>
        <div class="profile-subtitle">{{ site.data.profile.subtitle }}</div>
        <div class="profile-email">{{ site.data.profile.email }}</div>
        <div class="profile-links">
          <a href="{{ site.data.profile.links.cv }}">[CV]</a>
          <a href="{{ site.data.profile.links.scholar }}">[Google Scholar]</a>
          <a href="{{ site.data.profile.links.linkedin }}">[LinkedIn]</a>
        </div>
      </div>
    </div>

    <div class="card">
      <h2>NEWS</h2>
      <ul class="list list-dated">
        {% for item in site.data.news %}
        <li><span class="date">{{ item.date }}</span><span class="item-text">{{ item.text | markdownify | remove: "<p>" | remove: "</p>" }}</span></li>
        {% endfor %}
      </ul>
    </div>

    <div class="card">
      <h2>TALKS AND EVENTS</h2>
      <ul class="list">
        {% for item in site.data.talks %}
        <li>{{ item.text | markdownify | remove: "<p>" | remove: "</p>" }}</li>
        {% endfor %}
      </ul>
    </div>

    <div class="card">
      <h2>SELECTED AWARDS</h2>
      <ul class="list list-dated">
        {% for item in site.data.awards %}
        <li><span class="date">{{ item.date }}</span><span class="item-text">{{ item.text | markdownify | remove: "<p>" | remove: "</p>" }}</span></li>
        {% endfor %}
      </ul>
    </div>

    <div class="card">
      <h2>TEACHING & ACADEMIC SERVICE</h2>
      <ul class="list">
        {% for item in site.data.teaching %}
        <li>{{ item.text | markdownify | remove: "<p>" | remove: "</p>" }}</li>
        {% endfor %}
      </ul>
    </div>

    <div class="card">
      <h2>INDUSTRY EXPERIENCE</h2>
      <ul class="list">
        {% for item in site.data.industry %}
        <li>{{ item.text | markdownify | remove: "<p>" | remove: "</p>" }}</li>
        {% endfor %}
      </ul>
    </div>
  </aside>

  <main class="right-col">
    <section class="block">
      <h2>ABOUT</h2>
      <div class="block-text">{{ site.data.profile.about | markdownify }}</div>
    </section>

    <section class="block">
      <h2>RESEARCH INTERESTS</h2>
      <div class="block-text">{{ site.data.profile.research_interests | markdownify }}</div>
    </section>

    <section class="block">
      <h2>SELECTED PUBLICATIONS <span class="section-note">(* equal contributions)</span></h2>
      {% for pub in site.data.publications %}
      <div class="pub-card">
        <div class="pub-media">
          <img src="{{ pub.image | relative_url }}" alt="{{ pub.title }}">
          <div class="pub-links">
            {% for link in pub.links %}
            <a href="{{ link.url }}">[{{ link.label }}]</a>
            {% endfor %}
          </div>
        </div>
        <div class="pub-content">
          <div class="pub-title">{{ pub.title }}</div>
          <div class="pub-authors">{{ pub.authors }}</div>
          <div class="pub-venue">{{ pub.venue }}</div>
          <div class="pub-desc">{{ pub.description | markdownify | remove: "<p>" | remove: "</p>" }}</div>
        </div>
      </div>
      {% endfor %}
    </section>

    <section class="block">
      <h2>OTHER SELECTED DESIGN</h2>
      {% for design in site.data.designs %}
      <div class="pub-card">
        <div class="pub-media">
          <img src="{{ design.image | relative_url }}" alt="{{ design.title }}">
          <div class="pub-links">
            {% for link in design.links %}
            <a href="{{ link.url }}">[{{ link.label }}]</a>
            {% endfor %}
          </div>
        </div>
        <div class="pub-content">
          <div class="pub-title">{{ design.title }}</div>
          <div class="pub-authors">{{ design.authors }}</div>
          <div class="pub-venue">{{ design.venue }}</div>
          <div class="pub-desc">{{ design.description | markdownify | remove: "<p>" | remove: "</p>" }}</div>
        </div>
      </div>
      {% endfor %}
    </section>
  </main>
</div>
