---
permalink: /
title: "Chuxue Cao"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% assign sorted_publications = site.publications | sort: "date" | reverse %}
{% assign selected_papers = "" | split: "," %}
{% assign other_papers = "" | split: "," %}
{% for paper in sorted_publications %}
  {% if paper.teaser %}
    {% assign selected_papers = selected_papers | push: paper %}
  {% else %}
    {% assign other_papers = other_papers | push: paper %}
  {% endif %}
{% endfor %}

<div class="single-page">
  <section id="about" class="single-page__section" style="margin-top: 1rem;">
    <p class="single-page__lead" style="color: #111827; max-width: 100%;">
      Hi! I am a second-year PhD student at the Hong Kong University of Science and Technology, advised by
      <a href="https://facultyprofiles.hkust.edu.hk/profiles.php?profile=sirui-han-siruihan">Prof. Sirui Han</a>
      and <a href="https://facultyprofiles.hkust.edu.hk/profiles.php?profile=yike-guo-yikeguo">Prof. Yike Guo</a>.
      My research focuses on formal reasoning, AI for Mathematics, and LLM safety.
    </p>
  </section>

  <section id="research" class="single-page__section">
    <h2>Research</h2>
    <p class="research-summary">I study how language models can reason more reliably, verify their own intermediate steps, and behave safely in high-stakes settings. My work connects natural language reasoning with formal logic verification and theorem proving, aiming to build methods and benchmarks that push LLMs toward stronger mathematical problem solving and safe alignment in legal, multilingual, and domain-specific scenarios.</p>
  </section>

  <section id="publications" class="single-page__section">
    <h2>Selected Publications</h2>
    <div class="publication-grid">
      {% for paper in selected_papers %}
        {% include publication-card.html paper=paper %}
      {% endfor %}
    </div>
  </section>

  <section id="other-publications" class="single-page__section">
    <h2>Conference Papers</h2>
    <ul class="other-publications-list">
      {% for paper in other_papers %}
        {% if paper.category == 'conferences' %}
        {% assign paper_title = paper.title | markdownify | remove: "<p>" | remove: "</p>" %}
        <li>
          <strong>
            {% if paper.paperurl or paper.url %}
              <a href="{{ paper.paperurl | default: paper.url }}">{{ paper_title }}</a>
            {% else %}
              {{ paper_title }}
            {% endif %}
          </strong><br>
          {% if paper.authors %}{{ paper.authors }}<br>{% endif %}
          <em>{{ paper.venue }}</em>, {{ paper.date | date: "%Y" }}
        </li>
        {% endif %}
      {% endfor %}
    </ul>

    <h2 style="margin-top: 2.5rem;">Preprints</h2>
    <ul class="other-publications-list">
      {% for paper in other_papers %}
        {% if paper.category == 'manuscripts' %}
        {% assign paper_title = paper.title | markdownify | remove: "<p>" | remove: "</p>" %}
        <li>
          <strong>
            {% if paper.paperurl or paper.url %}
              <a href="{{ paper.paperurl | default: paper.url }}">{{ paper_title }}</a>
            {% else %}
              {{ paper_title }}
            {% endif %}
          </strong><br>
          {% if paper.authors %}{{ paper.authors }}<br>{% endif %}
          <em>{{ paper.venue }}</em>, {{ paper.date | date: "%Y" }}
        </li>
        {% endif %}
      {% endfor %}
    </ul>
  </section>

  <section id="contact" class="single-page__section">
    <h2>Contact</h2>
    <p>
      I am always happy to discuss research on formal reasoning, AI4Math, and LLM safety.
      You can reach me at <a href="mailto:{{ site.author.email }}">{{ site.author.email }}</a>.
    </p>
  </section>
</div>

