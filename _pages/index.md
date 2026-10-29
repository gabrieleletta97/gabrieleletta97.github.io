---
permalink: /
title:
author_profile: false
redirect_from:
  - /about/
  - /about.html
---

<section id="about" class="onepage-section onepage-hero" data-section="about">
  <header class="section-banner about-banner onepage-art-banner"><h1>Home</h1></header>
  <div class="onepage-hero__copy">
  <h1>Gabriele Letta</h1>
  <p class="onepage-lead">I am an applied economist working on policy evaluation, health economics and public economics.</p>
  <p>I obtained my <strong>PhD in Economics and Finance</strong> at <strong>Università Cattolica del Sacro Cuore — DEFAP School</strong> in 2026, supervised by <a href="https://docenti.unicatt.it/ppd2/it/docenti/12695/gilberto-turati">Gilberto Turati</a> and <a href="https://sites.google.com/view/luca-salmasi/home-page">Luca Salmasi</a>.</p>
  <p>In 2025 I was a visiting researcher at <strong>IEB — Universitat de Barcelona</strong>, hosted by <a href="https://www.juditvall.com/">Judit Vall Castelló</a>. I was born and raised in Rome and earned my MSc at Sapienza University of Rome in 2021.</p>
  <div class="onepage-interests"><span>Policy Evaluation</span><span>Health Economics</span><span>Public Economics</span></div>
  <div class="onepage-actions">
    <a class="academic-button academic-button--primary" href="{{ '/files/CV_Letta.pdf' | relative_url }}">Download CV</a>
    <a class="academic-button" href="#research">Research</a>
    <a class="onepage-text-link" href="mailto:gabriele.letta@unicatt.it">Email</a>
    <a class="onepage-text-link" href="https://www.linkedin.com/in/gabriele-letta-b0796a1b6/">LinkedIn</a>
    <a class="onepage-text-link" href="https://github.com/gabrieleletta97">GitHub</a>
  </div>
  </div>
  <figure class="onepage-hero__portrait"><img src="{{ '/images/Modified.jpg' | relative_url }}" alt="Gabriele Letta"></figure>
</section>

<section id="research" class="onepage-section onepage-research" data-section="research">
  <header class="section-banner research-banner onepage-art-banner"><h1>Research</h1></header>
  {% for category in site.publication_category %}
    {% assign category_posts = site.publications | where: "category", category[0] | reverse %}
    {% if category_posts.size > 0 and category[1].title %}
      <div class="onepage-research-group onepage-research-group--{{ category[0] }}"><h3>{{ category[1].title }}</h3>{% for post in category_posts %}{% unless post.homepage_last %}{% include onepage-publication.html post=post %}{% endunless %}{% endfor %}{% for post in category_posts %}{% if post.homepage_last %}{% include onepage-publication.html post=post %}{% endif %}{% endfor %}</div>
    {% endif %}
  {% endfor %}
</section>

{% assign presentations_page = site.pages | where: "permalink", "/presentations/" | first %}
<section id="presentations" class="onepage-section" data-section="presentations">
  <header class="section-banner presentations-banner onepage-art-banner"><h1>Presentations</h1></header>
  <div class="onepage-embedded onepage-presentations-list">{{ presentations_page.content | markdownify }}</div>
</section>

{% assign teaching_page = site.pages | where: "permalink", "/teaching/" | first %}
<section id="teaching" class="onepage-section" data-section="teaching">
  <header class="section-banner teaching-banner onepage-art-banner"><h1>Teaching</h1></header>
  <div class="onepage-embedded onepage-teaching-list">{{ teaching_page.content | markdownify }}</div>
</section>

<footer class="onepage-footer">
  <nav class="onepage-footer__nav" aria-label="More pages"><a href="{{ '/workshop/' | relative_url }}">Workshop →</a><a href="{{ '/other/' | relative_url }}">Other →</a></nav>
  <p>Gabriele Letta · <a href="mailto:gabriele.letta@unicatt.it">gabriele.letta@unicatt.it</a></p>
</footer>
