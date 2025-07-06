---
permalink: /
title: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---


Hi! I am a first-year PhD student at the Hong Kong University of Science and Technology. I am very fortunate to be advised by [Prof. Sirui Han](https://facultyprofiles.hkust.edu.hk/profiles.php?profile=sirui-han-siruihan) and [Prof. Yike Guo](https://facultyprofiles.hkust.edu.hk/profiles.php?profile=yike-guo-yikeguo). Previously, I received my Bachelor’s degree from Jilin University and my Master’s degree from the University of Hong Kong.

My research interests include AI for Mathematics (AI4Math), Formal Reasoning, and Large Language Model (LLM) Safety. 

## Publications
### Preprint
{% for publication in site.publications reversed %}
  {% if publication.category == 'manuscripts' %}
    * [**{{ publication.title }}**]({{ publication.paperurl }})  
      *Venue*: {{ publication.venue }}, {{ publication.date }}
  {% endif %}
{% endfor %}

### Conferences
{% for publication in site.publications reversed %}
  {% if publication.category == 'conferences' %}
    * [**{{ publication.title }}**]({{ publication.paperurl }})  
      *Venue*: {{ publication.venue }}, {{ publication.date }}
  {% endif %}
{% endfor %}
