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
    <p class="single-page__lead">
      <span class="lang-en">👋 Hi! I am a second-year PhD student at the Hong Kong University of Science and Technology, advised by
      <a href="https://facultyprofiles.hkust.edu.hk/profiles.php?profile=sirui-han-siruihan">Prof. Sirui Han</a>
      and <a href="https://facultyprofiles.hkust.edu.hk/profiles.php?profile=yike-guo-yikeguo">Prof. Yike Guo</a>.
      My research focuses on AI safety & alignment and formal reasoning.</span><span class="lang-zh">👋 哈喽！我是香港科技大学的二年级博士生，师从<a href="https://facultyprofiles.hkust.edu.hk/profiles.php?profile=sirui-han-siruihan">韩斯睿教授</a>和<a href="https://facultyprofiles.hkust.edu.hk/profiles.php?profile=yike-guo-yikeguo">郭毅可教授</a>。我的研究方向为大模型安全对齐（LLM Safety & Alignment）与形式化推理（Formal Reasoning）。</span>
    </p>
  </section>

  <section id="research" class="single-page__section">
    <h2><span class="lang-en">🔍 Research</span><span class="lang-zh">🔍 研究方向</span></h2>
    <p class="research-summary"><span class="lang-en">I study how language models can reason more reliably and safely. My work connects natural language reasoning with formal logic verification, aiming to build agentic post-training frameworks and benchmarks that push LLMs toward stronger logical reasoning and safe alignment.</span><span class="lang-zh">我主要研究大模型如何进行更可靠、安全的推理。我的工作将自然语言推理与形式化逻辑验证相结合，致力于后训练框架和安全评测基准，推动大模型向更可靠的逻辑推理与安全对齐发展。</span></p>
  </section>

  <section id="publications" class="single-page__section">
    <h2><span class="lang-en">🌟 Selected Publications</span><span class="lang-zh">🌟 代表性论文</span></h2>
    <div class="publication-grid">
      {% for paper in selected_papers %}
        {% include publication-card.html paper=paper %}
      {% endfor %}
    </div>
  </section>

  <section id="other-publications" class="single-page__section">
    <h2><span class="lang-en">📝 Conference Papers</span><span class="lang-zh">📝 会议论文</span></h2>
    <ul class="other-publications-list">
      {% for paper in other_papers %}
        {% if paper.category == 'conferences' %}
        {% assign paper_title = paper.title | markdownify | remove: "<p>" | remove: "</p>" %}
        <li>
          <strong>{{ paper_title }}</strong>
          {% if paper.paperurl or paper.url %}
            <a href="{{ paper.paperurl | default: paper.url }}" class="publication-card__resource-link" target="_blank" rel="noopener">[Paper]</a>
          {% endif %}
          {% if paper.codeurl %}
            <a href="{{ paper.codeurl }}" class="publication-card__resource-link" target="_blank" rel="noopener">[Code]</a>
          {% endif %}
          {% if paper.modelurl %}
            <a href="{{ paper.modelurl }}" class="publication-card__resource-link" target="_blank" rel="noopener">[Model]</a>
          {% endif %}
          <br>
          {% if paper.authors %}{{ paper.authors }}<br>{% endif %}
          <em>{{ paper.venue }}</em>, {{ paper.date | date: "%Y" }}
        </li>
        {% endif %}
      {% endfor %}
    </ul>

    <h2 style="margin-top: 2.5rem;"><span class="lang-en">🚀 Preprints</span><span class="lang-zh">🚀 预印本</span></h2>
    <ul class="other-publications-list">
      {% for paper in other_papers %}
        {% if paper.category == 'manuscripts' %}
        {% assign paper_title = paper.title | markdownify | remove: "<p>" | remove: "</p>" %}
        <li>
          <strong>{{ paper_title }}</strong>
          {% if paper.paperurl or paper.url %}
            <a href="{{ paper.paperurl | default: paper.url }}" class="publication-card__resource-link" target="_blank" rel="noopener">[Paper]</a>
          {% endif %}
          {% if paper.codeurl %}
            <a href="{{ paper.codeurl }}" class="publication-card__resource-link" target="_blank" rel="noopener">[Code]</a>
          {% endif %}
          {% if paper.modelurl %}
            <a href="{{ paper.modelurl }}" class="publication-card__resource-link" target="_blank" rel="noopener">[Model]</a>
          {% endif %}
          <br>
          {% if paper.authors %}{{ paper.authors }}<br>{% endif %}
          <em>{{ paper.venue }}</em>, {{ paper.date | date: "%Y" }}
        </li>
        {% endif %}
      {% endfor %}
    </ul>
  </section>

  <section id="education" class="single-page__section">
    <h2><span class="lang-en">🎓 Education</span><span class="lang-zh">🎓 教育背景</span></h2>
    <div class="resume-list">
      <div class="resume-item">
        <div class="resume-item__date"><span class="lang-en">September 2024 - Now</span><span class="lang-zh">2024年9月 - 至今</span></div>
        <div class="resume-item__content">
          <div class="resume-item__header">
            <strong><span class="lang-en">Hong Kong University of Science and Technology</span><span class="lang-zh">香港科技大学</span></strong>
          </div>
          <div class="resume-item__body">
            <span class="lang-en">PhD student, Supervisors: Prof. Sirui Han, Prof. Yike Guo</span><span class="lang-zh">博士生，导师：韩斯睿教授、郭毅可教授</span><br>
            <span class="lang-en">Division of Emerging Interdisciplinary Areas, Academy of Interdisciplinary Studies</span><span class="lang-zh">跨学科综合学院 新兴跨学科领域学部</span>
          </div>
        </div>
      </div>
      
      <div class="resume-item">
        <div class="resume-item__date"><span class="lang-en">September 2022 - January 2024</span><span class="lang-zh">2022年9月 - 2024年1月</span></div>
        <div class="resume-item__content">
          <div class="resume-item__header">
            <strong><span class="lang-en">The University of Hong Kong</span><span class="lang-zh">香港大学</span></strong>
          </div>
          <div class="resume-item__body">
            <span class="lang-en">Master's Degree</span><span class="lang-zh">硕士</span><br>
            <span class="lang-en">MSc Artificial Intelligence, Faculty of Science</span><span class="lang-zh">理学院 人工智能理学硕士</span>
          </div>
        </div>
      </div>
      
      <div class="resume-item">
        <div class="resume-item__date"><span class="lang-en">September 2018 - July 2022</span><span class="lang-zh">2018年9月 - 2022年7月</span></div>
        <div class="resume-item__content">
          <div class="resume-item__header">
            <strong><span class="lang-en">Jilin University</span><span class="lang-zh">吉林大学</span></strong>
          </div>
          <div class="resume-item__body">
            <span class="lang-en">Bachelor's Degree (Honours), Supervisors: Prof. Renchu Guan, Prof. Xiaoyue Feng</span><span class="lang-zh">学士 (荣誉学位)，导师：管仁初教授、丰小月教授</span><br>
            <span class="lang-en">Software Engineering (Pilot class), College of Software Engineering</span><span class="lang-zh">软件学院 软件工程（实验班）</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="experience" class="single-page__section">
    <h2><span class="lang-en">💼 Experience</span><span class="lang-zh">💼 工作经历</span></h2>
    <div class="resume-list">
      <div class="resume-item">
        <div class="resume-item__date"><span class="lang-en">October 2025 - February 2026</span><span class="lang-zh">2025年10月 - 2026年2月</span></div>
        <div class="resume-item__content">
          <div class="resume-item__header">
            <strong><span class="lang-en">Shanghai Artificial Intelligence Laboratory</span><span class="lang-zh">上海人工智能实验室</span></strong>
          </div>
          <div class="resume-item__body">
            <span class="lang-en">Research Intern, Mentor: Lijun Wu</span><span class="lang-zh">研究实习生，导师：吴郦军</span><br>
            OpenDataLab, OpenDataArena
          </div>
        </div>
      </div>

      <div class="resume-item">
        <div class="resume-item__date"><span class="lang-en">September 2023 - August 2024</span><span class="lang-zh">2023年9月 - 2024年8月</span></div>
        <div class="resume-item__content">
          <div class="resume-item__header">
            <strong><span class="lang-en">The University of Hong Kong</span><span class="lang-zh">香港大学</span></strong>
          </div>
          <div class="resume-item__body">
            <span class="lang-en">Research Assistant, Supervisor: Prof. Hailiang Chen</span><span class="lang-zh">研究助理，导师：陈海亮教授</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="contact" class="single-page__section">
    <h2><span class="lang-en">📬 Contact</span><span class="lang-zh">📬 联系我</span></h2>
    <p>
      <span class="lang-en">I’m always open to discussing research-related topics. Feel free to reach me at </span><span class="lang-zh">欢迎交流～📮</span><a href="mailto:{{ site.author.email }}">{{ site.author.email }}</a>.
    </p>
  </section>
</div>

