---
layout: page
title: Notes & Resources
permalink: /notes/
nav: true
nav_order: 3
description: Course notes, study materials, and tex resources.


# ===== 第一部分：笔记（卡片形式）=====
notes:
  - title: "Maths for Economists"
    description: "This is a handbook of all maths knowledge that economic students need, which contains basics of analysis, algebra, topology and their applications with an emphasis on maths foundations of economic theory."
    pdf:
      name: "Maths for Economists"
      file: "assets/pdf/Maths-for-Economists.pdf"
    repo:
      name: "tex code"
      url: "https://github.com/guo-zhenran/Maths-for-Economists"

# ===== 第二部分：兴趣主题（列表形式，增加 notes PDF 链接）=====
topics_in_interest:
  - title: "Coordination"
    reading_list: "assets/bib/Coordination.bib"
    notes: "assets/pdf/deep_learning_notes.pdf"  
  - title: "Matching Theory"
    reading_list: "assets/bib/matching_incom_info.bib"
    notes: "assets/pdf/deep_learning_notes.pdf"
  - title: "Cheap Talk"
    reading_list: "assets/bib/cheap_talk.bib"
    notes: "assets/pdf/deep_learning_notes.pdf"
  

# ===== 第三部分：TeX 模板（列表形式，支持 subs 嵌套）=====
tex_template:
  - title: "My TeX Template"
    description: "A comprehensive LaTeX template for academic needs. Please click the button for tex codes."
    repo: "https://github.com/guo-zhenran/myTemplate"
    subs:
      - title: "myBook"
        description: 'The template is based on Agni Datta''s <a href="https://www.overleaf.com/latex/templates/preprint-book-manuscript-template/ghrbwppzhzjx" rel="noopener noreferrer">“Preprint Book Manuscript Template”</a>, which I have modified to fit my requirements. The famous <a href="https://github.com/ElegantLaTeX/ElegantLaTeX" rel="noopener noreferrer"> ElegantLaTeX</a> template has also inspired me greatly.'
        exp: "assets/pdf/exampleBook.pdf"
      - title: "myPresentation"
        description: 'Inspired by <a href="https://www.overleaf.com/latex/templates/elegant-slides/yfqyhpprvdmg" rel="noopener noreferrer">“Elegant Slides”</a>, I wrote this minimalistic template with an elegant blue based on Beamer''s template boxes. See the example for customized features of this template.'
        exp: "assets/pdf/examplePre.pdf"
      - title: "myPaper"
---

{% if page.notes or page.topics_in_interest or page.tex_template %}

<style>
/* ========= 卡片样式（与之前完全一致）========= */
.resource-cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.resource-card {
  background: var(--global-bg-color);
  border: 1px solid var(--global-divider-color);
  border-radius: 10px;
  overflow: hidden;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  display: flex;
  flex-direction: column;
}

.resource-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 18px rgba(0,0,0,0.1);
}

.card-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 1.5rem;
  flex-wrap: wrap;
  gap: 0.5rem 1rem;
}

.card-title {
  margin: 0;
  font-size: 1.4rem;
  font-weight: normal;
  color: var(--global-text-color);
  flex: 1 1 auto;
}

.card-actions {
  display: flex;
  gap: 1rem;
  align-items: center;
  flex-wrap: wrap;
}

.action-link {
  background: none;
  border: none;
  padding: 0;
  font-size: 0.9rem;
  color: #5B7A90;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 0.3rem;
  transition: color 0.2s ease;
  white-space: nowrap;
}

.action-link i {
  font-size: 1rem;
}

.action-link:hover {
  color: var(--global-theme-color);
  text-decoration: underline;
}

.card-body {
  padding: 1.5rem;
  flex: 1;
  display: flex;
  align-items: center;
}

.description {
  margin: 0;
  color: var(--global-text-color-light);
  line-height: 1.5;
  width: 100%;
}

/* ========= 列表样式（用于 topics_in_interest 和 tex_template）========= */
.simple-list {
  margin: 1.5rem 0 2rem 0;
  padding-left: 1.8rem;
  list-style-type: disc;
}

.simple-list li {
  margin-bottom: 0.75rem;
  line-height: 1.5;
}

.list-title {
  font-weight: 600;
  color: var(--global-text-color);
}

.list-desc {
  color: var(--global-text-color-light);
  font-size: 0.9rem;
  margin-left: 0.5rem;
}

.list-link {
  margin-left: 0.5rem;
  font-size: 0.85rem;
}

.list-link a {
  color: #5B7A90;
  text-decoration: none;
}

.list-link a:hover {
  color: var(--global-theme-color);
  text-decoration: underline;
}

/* 嵌套子列表样式 */
.nested-list {
  margin: 0.5rem 0 0.25rem 1.5rem;
  padding-left: 0;
  list-style-type: circle;
}

.nested-list li {
  margin-bottom: 0.4rem;
}

.nested-list .list-desc {
  margin-left: 0.3rem;
}

.section-title {
  margin-top: 1.5rem;
  border-bottom: 2px solid var(--global-divider-color);
  padding-bottom: 0.3rem;
  font-size: 1.8rem;
  font-weight: 500;
}

@media (max-width: 600px) {
  .resource-cards {
    grid-template-columns: 1fr;
  }
}
</style>

<!-- ========= 1. NOTES（卡片形式）========= -->
{% if page.notes and page.notes.size > 0 %}
<h2 class="section-title">Notes</h2>
<div class="resource-cards">
  {% for item in page.notes %}
  <div class="resource-card">
    <div class="card-header">
      <h3 class="card-title">{{ item.title }}</h3>
      <div class="card-actions">
        {% if item.pdf %}
        <a href="{{ item.pdf.file | relative_url }}" class="action-link pdf-link" target="_blank">
          <i class="fas fa-file-pdf"></i> PDF
        </a>
        {% endif %}
        {% if item.repo %}
        <a href="{{ item.repo.url }}" class="action-link repo-link" target="_blank">
          <i class="fab fa-github"></i> TEX Code
        </a>
        {% endif %}
      </div>
    </div>
    <div class="card-body">
      <p class="description">{{ item.description }}</p>
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

<!-- ========= 2. TOPICS IN INTEREST（列表形式，增加 notes PDF）========= -->
{% if page.topics_in_interest and page.topics_in_interest.size > 0 %}
<h2 class="section-title">Topics in Interest (under construction)</h2>
<ul class="simple-list">
  {% for topic in page.topics_in_interest %}
  <li>
    <span class="list-title">{{ topic.title }}</span>
    {% if topic.reading_list %}
<span class="list-link">
  <a href="{{ topic.reading_list | relative_url }}" class="action-link" target="_blank">
    <i class="fas fa-book"></i> reading list
  </a>
</span>
{% endif %}
{% if topic.notes %}
<span class="list-link">
  <a href="{{ topic.notes | relative_url }}" class="action-link" target="_blank">
    <i class="fas fa-file-pdf"></i> notes
  </a>
</span>
{% endif %}
  </li>
  {% endfor %}
</ul>
{% endif %}

<!--
<!-- ========= 3. TEX TEMPLATE（列表形式，支持 subs 嵌套）========= 
{% if page.tex_template and page.tex_template.size > 0 %}
<h2 class="section-title">TeX Templates</h2>
<ul class="simple-list">
  {% for template in page.tex_template %}
  <li>
    <span class="list-title">{{ template.title }}</span>
    {% if template.description %}
    <span class="list-desc">– {{ template.description }}</span>
    {% endif %}
    {% if template.repo %}
<span class="list-link">
  <a href="{{ template.repo }}" class="action-link" target="_blank">
    <i class="fab fa-github"></i> GitHub
  </a>
</span>
{% endif %}
    {% if template.subs and template.subs.size > 0 %}
    <ul class="nested-list">
      {% for sub in template.subs %}
      <li>
        <span class="list-title">{{ sub.title }}</span>
        {% if sub.description %}
        <span class="list-desc">– {{ sub.description }}</span>
        {% endif %}
        {% if sub.exp %}
<span class="list-link">
  <a href="{{ sub.exp | relative_url }}" class="action-link" target="_blank">
    <i class="fas fa-file-pdf"></i> example
  </a>
</span>
{% endif %}
      </li>
      {% endfor %}
    </ul>
    {% endif %}
  </li>
  {% endfor %}
</ul>
{% endif %}

{% endif %}
-->