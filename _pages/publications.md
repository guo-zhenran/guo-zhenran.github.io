---
layout: page
permalink: /research/
title: Research
description: My research interest lies in Microeconomic Theory, with a focus on Behavioral and Experimental Economics.
nav: true
nav_order: 2

publications:
  - title: ""
    coauthors: ""
    published_at: ""
    year: ""
    abstract: ""
    pdf: ""
    data: ""
    talked_at: ""
    pre_slides: ""

working_papers:
  - title: ""
    coauthors: ""
    state: ""
    latest_version: ""
    abstract: ""
    pdf: ""
    ssrn: ""
    talked_at: ""
    pre_slides: ""

working_in_progress:
  - title: "Match to Interact"
    coauthors: '<a href="http://www.hesimin.com" rel="noopener noreferrer">“Simin He”</a> and <a href="https://sites.google.com/site/jiabinwuecon/home" rel="noopener noreferrer">“Jiabin Wu”</a>'
---

{% if page.publications or page.working_papers or page.working_in_progress %}

<style>
/* 复用你原有的卡片样式，并增加灰色头部和布局微调 */
.research-cards {
  gap: 1.5rem;
  margin: 1.5rem 0 2rem 0;
}

.research-card {
  background: var(--global-bg-color);
  border: 1px solid var(--global-divider-color);
  border-radius: 12px;
  overflow: hidden;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  display: flex;
  flex-direction: column;
}

.research-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 20px rgba(0,0,0,0.1);
}

/* 灰色卡片头部 */
.card-header-gray {
  background-color: var(--global-card-header-bg, #f5f5f5);
  padding: 1rem 1.2rem;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  gap: 0.8rem;
  border-bottom: 1px solid var(--global-divider-color);
}

.card-header-gray .card-title {
  margin: 0;
  font-size: 1.25rem;
  font-weight: 500;
  color: var(--global-text-color);
  flex: 1;
}

.card-actions {
  display: flex;
  gap: 0.8rem;
  flex-wrap: wrap;
}

.action-btn {
  background: none;
  border: none;
  font-size: 0.85rem;
  color: #5B7A90;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  gap: 0.3rem;
  transition: color 0.2s;
}

.action-btn i {
  font-size: 0.9rem;
}

.action-btn:hover {
  color: var(--global-theme-color);
  text-decoration: underline;
}

/* 白色内容区域 */
.card-content {
  padding: 1.2rem;
  flex: 1;
}

.coauthors-line, .presented-line {
  margin: 0 0 0.5rem 0;
  font-size: 0.9rem;
  color: var(--global-text-color);
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 0.5rem;
}

.presented-line .action-btn {
  margin-left: 0.25rem;
}

.abstract-label {
  font-weight: bold;
  margin: 0.75rem 0 0.2rem 0;
}

.abstract-text {
  margin: 0;
  font-size: 0.9rem;
  line-height: 1.4;
  color: var(--global-text-color-light);
}

/* 简单列表样式 */
.simple-list {
  margin: 1rem 0 2rem 0;
  padding-left: 1.5rem;
}

.simple-list li {
  margin-bottom: 0.6rem;
  line-height: 1.4;
}

.simple-list li strong {
  font-weight: 600;
}

/* 板块标题 */
.section-title {
  margin-top: 1.5rem;
  border-bottom: 2px solid var(--global-divider-color);
  padding-bottom: 0.3rem;
  font-size: 1.8rem;
  font-weight: 500;
}

/* 小屏幕优化 */
@media (max-width: 600px) {
  .research-cards {
    grid-template-columns: 1fr;
  }
}
</style>

<!-- =========  PUBLICATIONS  ========= -->
{% if page.publications and page.publications.size > 0 %}
<h2 class="section-title">Publications (Under Construction)</h2>
<div class="research-cards">
  {% for pub in page.publications %}
  <div class="research-card">
    <div class="card-header-gray">
      <div class="card-title">{{ pub.title }}</div>
      <div class="card-actions">
        {% if pub.pdf %}
        <a href="{{ pub.pdf | relative_url }}" class="action-btn" target="_blank">
          <i class="fas fa-file-pdf"></i> PDF
        </a>
        {% endif %}
        {% if pub.data %}
        <a href="{{ pub.data }}" class="action-btn" target="_blank">
          <i class="fas fa-database"></i> Data
        </a>
        {% endif %}
      </div>
    </div>
    <div class="card-content">
      <div class="coauthors-line">
        with {{ pub.coauthors }}, published at {{ pub.published_at }}, {{pub.year}}.
      </div>
      {% if pub.abstract %}
      <div class="abstract-label">Abstract:</div>
      <div class="abstract-text">{{ pub.abstract }}</div>
      {% endif %}

      <!-- 新增：Presented at 和 Slides -->
      {% if pub.talked_at or pub.pre_slides %}
      <div class="presented-line">
        {% if pub.talked_at %}Presented at {{ pub.talked_at }}.{% endif %}
        {% if pub.pre_slides %}
        <a href="{{ pub.pre_slides | relative_url }}" class="action-btn" target="_blank">
          <i class="fas fa-file-pdf"></i> Slides
        </a>
        {% endif %}
      </div>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

<!-- =========  WORKING PAPERS  ========= -->
{% if page.working_papers and page.working_papers.size > 0 %}
<h2 class="section-title">Working Papers (Under Construction)</h2>
<div class="research-cards">
  {% for wp in page.working_papers %}
  <div class="research-card">
    <div class="card-header-gray">
      <div class="card-title">{{ wp.title }}</div>
      <div class="card-actions">
        {% if wp.pdf %}
        <a href="{{ wp.pdf | relative_url }}" class="action-btn" target="_blank">
          <i class="fas fa-file-pdf"></i> PDF
        </a>
        {% endif %}
        {% if wp.ssrn %}
        <a href="{{ wp.ssrn }}" class="action-btn" target="_blank">
          <i class="fas fa-external-link-alt"></i> SSRN
        </a>
        {% endif %}
      </div>
    </div>
    <div class="card-content">
      <div class="coauthors-line">
        with {{ wp.coauthors }}, {% if wp.latest_version %} latest version: {{ wp.latest_version }}{% endif %}{% if wp.state %}, {{ wp.state }}{% endif %}.
      </div>
      {% if wp.abstract %}
      <div class="abstract-label">Abstract:</div>
      <div class="abstract-text">{{ wp.abstract }}</div>
      {% endif %}

      <!-- 新增：Presented at 和 Slides -->
      {% if wp.talked_at or wp.pre_slides %}
      <div class="presented-line">
        {% if wp.talked_at %}Presented at {{ wp.talked_at }}.{% endif %}
        {% if wp.pre_slides %}
        <a href="{{ wp.pre_slides | relative_url }}" class="action-btn" target="_blank">
          <i class="fas fa-file-pdf"></i> Slides
        </a>
        {% endif %}
      </div>
      {% endif %}
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

<!-- =========  WORK IN PROGRESS  ========= -->
{% if page.working_in_progress and page.working_in_progress.size > 0 %}
<h2 class="section-title">Working in Progress</h2>
<ul class="simple-list">
  {% for wip in page.working_in_progress %}
  <li><strong>{{ wip.title }}</strong> {% if wip.coauthors %} (with {{ wip.coauthors }}).{% endif %}</li>
  {% endfor %}
</ul>
{% endif %}

{% endif %}
