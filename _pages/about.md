---
permalink: /
title: "Chuxue Cao"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% assign sorted_publications = site.publications | sort: "date" | reverse %}

<div class="single-page">
  <section id="about" class="single-page__hero">
    <div class="single-page__eyebrow">PhD Student - HKUST</div>
    <h1>Reasoning, safety, and trustworthy language models.</h1>
    <p class="single-page__lead">
      Hi! I am a second-year PhD student at the Hong Kong University of Science and Technology, advised by
      <a href="https://facultyprofiles.hkust.edu.hk/profiles.php?profile=sirui-han-siruihan">Prof. Sirui Han</a>
      and <a href="https://facultyprofiles.hkust.edu.hk/profiles.php?profile=yike-guo-yikeguo">Prof. Yike Guo</a>.
      My research focuses on formal reasoning, AI for Mathematics, and LLM safety.
    </p>
    <div class="single-page__actions">
      <a class="single-page__button" href="#publications">View Publications</a>
      <a class="single-page__button single-page__button--ghost" href="{{ site.author.googlescholar }}">Google Scholar</a>
    </div>
  </section>

  <section id="research" class="single-page__section">
    <h2>Research</h2>
    <p>I study how language models can reason more reliably, verify their own intermediate steps, and behave safely in high-stakes settings.</p>
    <div class="research-grid">
      <div class="research-card">
        <h3>Formal Reasoning</h3>
        <p>Connecting natural language reasoning with formal logic verification, theorem proving, and symbolic feedback.</p>
      </div>
      <div class="research-card">
        <h3>AI for Mathematics</h3>
        <p>Building methods and benchmarks that push LLMs toward stronger mathematical problem solving.</p>
      </div>
      <div class="research-card">
        <h3>LLM Safety</h3>
        <p>Evaluating and aligning models for safer behavior in legal, multilingual, and domain-specific scenarios.</p>
      </div>
    </div>
  </section>

  <section id="publications" class="single-page__section">
    <h2>Selected Publications</h2>
    <p>Recent work across formal verification, reasoning benchmarks, safety evaluation, and domain-specific language models.</p>
    <div class="publication-grid">
      {% for paper in sorted_publications %}
        {% include publication-card.html paper=paper %}
      {% endfor %}
    </div>
  </section>

  <section id="contact" class="single-page__section">
    <h2>Contact</h2>
    <div class="contact-panel">
      I am always happy to discuss research on formal reasoning, AI4Math, and LLM safety.
      You can reach me at <a href="mailto:{{ site.author.email }}">{{ site.author.email }}</a>.
    </div>
  </section>
</div>

