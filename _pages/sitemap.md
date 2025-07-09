---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

<p>사이트에 포함된 모든 페이지와 글을 정리한 사이트맵입니다.<br>
검색 엔진용 <a href="{{ base_path }}/sitemap.xml" target="_blank">XML 버전</a>도 제공됩니다.</p>

<!-- ✅ Pages -->
<div class="sitemap-section">
  <h2>📄 Pages</h2>
  {% for page in site.pages %}
    {% unless page.title == nil or page.title == "Page Not Found" %}
      <div class="sitemap-item">
        <a href="{{ page.url | relative_url }}">{{ page.title }}</a><br>
        {% if page.date %}
          <small>{{ page.date | date: "%Y-%m-%d" }}</small>
        {% endif %}
      </div>
    {% endunless %}
  {% endfor %}
</div>

