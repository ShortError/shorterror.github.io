---
layout: page
title: What’s on My Mind?
permalink: /blog/
---

<style>
  .blog-intro {
    color: #a1a1aa;
    font-size: 16px;
    margin-top: -12px;
    margin-bottom: 32px;
  }

  html[data-theme="light"] .blog-intro {
    color: #52525b;
  }

  .modern-post-list {
    list-style: none;
    margin-left: 0;
    padding: 0;
  }

  .modern-post-item {
    padding: 24px 0;
    border-top: 1px solid #27272a;
    transition: transform 0.15s ease;
  }

  .modern-post-item:last-child {
    border-bottom: 1px solid #27272a;
  }

  html[data-theme="light"] .modern-post-item,
  html[data-theme="light"] .modern-post-item:last-child {
    border-color: #e4e4e7;
  }

  .modern-post-meta {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 13px;
    color: #a1a1aa;
    margin-bottom: 6px;
    text-transform: uppercase;
    letter-spacing: 0.04em;
  }

  html[data-theme="light"] .modern-post-meta {
    color: #71717a;
  }

  .modern-post-title {
    margin: 0 0 8px 0 !important;
    font-size: 22px;
    font-weight: 600;
    line-height: 1.35;
  }

  .modern-post-title a {
    color: #f4f4f5 !important;
    text-decoration: none;
    transition: color 0.15s ease;
  }

  .modern-post-title a:hover {
    color: #60a5fa !important;
  }

  html[data-theme="light"] .modern-post-title a {
    color: #18181b !important;
  }

  html[data-theme="light"] .modern-post-title a:hover {
    color: #2563eb !important;
  }

  .modern-post-excerpt {
    color: #a1a1aa;
    font-size: 15px;
    line-height: 1.6;
    margin: 0 0 12px 0;
  }

  html[data-theme="light"] .modern-post-excerpt {
    color: #52525b;
  }

  .modern-read-more {
    font-size: 14px;
    font-weight: 500;
    color: #60a5fa !important;
    text-decoration: none;
    display: inline-flex;
    align-items: center;
    gap: 4px;
  }

  .modern-read-more:hover {
    text-decoration: underline;
  }

  html[data-theme="light"] .modern-read-more {
    color: #2563eb !important;
  }
</style>

<p class="blog-intro">Notes, essays, and thoughts on technology, code, and everything in between.</p>

<ul class="modern-post-list">
  {%- for post in site.posts -%}
    {%- assign words = post.content | number_of_words -%}
    {%- assign mins = words | divided_by: 200 | plus: 1 -%}
    <li class="modern-post-item">
      <div class="modern-post-meta">
        <span>{{ post.date | date: "%b %-d, %Y" }}</span>
        <span>•</span>
        <span>{{ mins }} min read</span>
      </div>
      <h2 class="modern-post-title">
        <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
      </h2>
      {%- if post.excerpt -%}
        <p class="modern-post-excerpt">{{ post.excerpt | strip_html | truncatewords: 28 }}</p>
      {%- endif -%}
      <a class="modern-read-more" href="{{ post.url | relative_url }}">Read article →</a>
    </li>
  {%- endfor -%}
</ul>
