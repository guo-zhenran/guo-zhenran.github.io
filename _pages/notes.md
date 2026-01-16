---
layout: page
title: Notes & Resources  # 页面标题
permalink: /notes/  # 页面访问路径
nav: true  # 显示在导航栏
nav_order: 3  # 导航栏顺序（根据你现有页面调整）
description: Course notes, study materials, and tex resources.

pdf_downloads:
  - name: Maths for Economists.pdf  # 显示名称
    file: assets/pdf/Maths for Economists.pdf  # 文件路径
    description: "This is a handbook of all maths knowledge that economic students need, which contains basics of analysis, algebra, topology and their applications with emphasis on maths foundations of economic theory."


github_links:
  - name: tex code for "Maths for Economists"
    url: https://github.com/guo-zhenran/Maths-for-Economists
    description: "See my repository for the tex code."

---

<!-- PDF下载部分 -->
{% if page.pdf_downloads %}
# PDFs
<div class="pdf-downloads">
  {% for pdf in page.pdf_downloads %}
  <div class="pdf-item">
    <div class="pdf-icon">
      <i class="fas fa-file-pdf"></i>
    </div>
    <div class="pdf-info">
      <h4>{{ pdf.name }}</h4>
      <p>{{ pdf.description }}</p>
      <a href="{{ pdf.file | relative_url }}" class="btn btn-primary btn-sm" target="_blank">
        <i class="fas fa-download"></i> Download PDF
      </a>
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

<!-- GitHub链接部分 -->
{% if page.github_links %}
# Tex Code Recourses
<div class="github-links">
  {% for repo in page.github_links %}
  <div class="repo-item">
    <div class="repo-icon">
      <i class="fab fa-github"></i>
    </div>
    <div class="repo-info">
      <h4>
      <a href="{{ repo.url }}" target="_blank">{{ repo.name }}</a>
      </h4>
      <p>{{ repo.description }}</p>
      <a href="{{ repo.url }}" class="btn btn-outline-secondary btn-sm" target="_blank">
        <i class="fab fa-github"></i> View Repository
      </a>
    </div>
  </div>
  {% endfor %}
</div>
{% endif %}

<style>
/* 自定义样式 */
.pdf-downloads, .github-links {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  margin: 2rem 0;
}

.pdf-item, .repo-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  padding: 1.5rem;
  background: var(--global-bg-color);
  border: 1px solid var(--global-border-color);
  border-radius: 8px;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.pdf-item:hover, .repo-item:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.pdf-icon, .repo-icon {
  font-size: 1.5rem;
  color: var(--global-theme-color);
  min-width: 40px;
}

.pdf-info h4, .repo-info h4 {
  margin: 0 0 0.5rem 0;
  color: var(--global-text-color);
}

.pdf-info p, .repo-info p {
  margin: 0 0 1rem 0;
  color: var(--global-text-color-light);
}

.btn-primary {
  background-color: var(--global-theme-color);
  border-color: var(--global-theme-color);
}

.btn-primary:hover {
  background-color: var(--global-hover-color);
  border-color: var(--global-hover-color);
}
</style>
