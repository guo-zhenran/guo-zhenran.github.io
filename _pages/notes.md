---
layout: page
title: Notes & Resources
permalink: /notes/
nav: true
nav_order: 3
description: Course notes, study materials, and tex resources.

resources:
  - title: Maths for Economists
    description: "This is a handbook of all maths knowledge that economic students need, which contains basics of analysis, algebra, topology and their applications with emphasis on maths foundations of economic theory."
    pdf:
      name: Maths for Economists.pdf
      file: assets/pdf/Maths for Economists.pdf
    repo:
      name: tex code
      url: https://github.com/guo-zhenran/Maths-for-Economists
      
---

{% if page.resources %}
<h1>Notes</h1>
<div class="resource-cards">
  {% for item in page.resources %}
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

<style>
/* 卡片容器：使用 Grid 实现响应式多列布局 */
.resource-cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

/* 单个卡片 */
.resource-card {
  background: var(--global-bg-color);
  border: 1px solid var(--global-divider-color);
  border-radius: 10px;
  overflow: hidden;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  display: flex;
  flex-direction: column;  /* 确保内容垂直排列 */
}

.resource-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 18px rgba(0,0,0,0.1);
}

/* 卡片头部：标题和按钮行，支持换行 */
.card-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1rem 1.5rem;
  border-bottom: none;
  flex-wrap: wrap;         /* 宽度不足时按钮换到下一行 */
  gap: 0.5rem 1rem;        /* 行间距和列间距 */
}

.card-title {
  margin: 0;
  font-size: 1.4rem;
  font-weight: normal;
  color:#5B7A90;
  flex: 1 1 auto;          /* 标题尽可能占据剩余空间 */
}

.card-actions {
  display: flex;
  gap: 1rem;
  align-items: center;
  flex-wrap: wrap;         /* 按钮组内部也可换行 */
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
  white-space: nowrap;     /* 防止按钮文字换行 */
}

.action-link i {
  font-size: 1rem;
}

.action-link:hover {
  color: var(--global-theme-color);
  text-decoration: underline;
}

.card-body {
  padding: 1.5rem;          /* 上下左右统一内边距，文字自然居中留白 */
  flex: 1;
  display: flex;
  align-items: center;      /* 如果希望文字块垂直居中，但需配合高度 */
}

.description {
  margin: 0;
  color: var(--global-text-color-light);
  line-height: 1.5;
  width: 100%;              /* 保证描述文字占满宽度 */
}

/* 小屏幕时调整为单列（保持可读性） */
@media (max-width: 600px) {
  .resource-cards {
    grid-template-columns: 1fr;  /* 单列 */
  }
}
</style>