---
layout: page
permalink: /blog/
---

<style>
  /* Hide Minima's default page title */
  .post-header {
    display: none;
  }

  .medium-feed {
    max-width: 720px;
    margin: 0 auto;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  }

  /* Top Medium-Style Tab Header */
  .medium-tabs {
    display: flex;
    gap: 24px;
    border-bottom: 1px solid #27272a;
    margin-bottom: 8px;
  }

  html[data-theme="light"] .medium-tabs {
    border-bottom-color: #e4e4e7;
  }

  .medium-tab {
    font-size: 14px;
    font-weight: 500;
    padding: 12px 0;
    color: #f4f4f5;
    border-bottom: 2px solid #f4f4f5;
    margin-bottom: -1px;
  }

  html[data-theme="light"] .medium-tab {
    color: #18181b;
    border-bottom-color: #18181b;
  }

  /* Article Row */
  .medium-article {
    padding: 28px 0;
    border-bottom: 1px solid #27272a;
  }

  html[data-theme="light"] .medium-article {
    border-bottom-color: #f4f4f5;
  }

  /* Author Row (Avatar + Name + Date) */
  .medium-author-row {
    display: flex;
    align-items: center;
    gap: 8px;
    margin-bottom: 10px;
    font-size: 13px;
  }

  .medium-avatar {
    width: 24px;
    height: 24px;
    border-radius: 50%;
    background: linear-gradient(135deg, #3b82f6, #8b5cf6);
    color: #ffffff;
    font-size: 12px;
    font-weight: 700;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    text-transform: uppercase;
  }

  .medium-author-name {
    font-weight: 500;
    color: #e4e4e7;
  }

  html[data-theme="light"] .medium-author-name {
    color: #18181b;
  }

  .medium-date {
    color: #a1a1aa;
  }

  html[data-theme="light"] .medium-date {
    color: #71717a;
  }

  /* Content + Right Thumbnail Split */
  .medium-body {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 28px;
  }

  .medium-text {
    flex: 1;
    min-width: 0;
  }

  .medium-title {
    font-size: 22px;
    font-weight: 700;
    line-height: 1.28;
    letter-spacing: -0.015em;
    margin: 0 0 8px 0 !important;
  }

  .medium-title a {
    color: #f4f4f5 !important;
    text-decoration: none;
  }

  .medium-title a:hover {
    opacity: 0.85;
  }

  html[data-theme="light"] .medium-title a {
    color: #18181b !important;
  }

  .medium-excerpt {
    font-family: Georgia, "Times New Roman", serif;
    font-size: 15.5px;
    line-height: 1.55;
    color: #a1a1aa;
    margin: 0 0 16px 0;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  html[data-theme="light"] .medium-excerpt {
    color: #52525b;
  }

  /* Footer Metadata (Tag Pill + Read Time) */
  .medium-footer {
    display: flex;
    align-items: center;
    gap: 10px;
    font-size: 13px;
    color: #a1a1aa;
  }

  html[data-theme="light"] .medium-footer {
    color: #71717a;
  }

  .medium-pill {
    background-color: #27272a;
    color: #d4d4d8;
    padding: 3px 10px;
    border-radius: 999px;
    font-size: 12px;
  }

  html[data-theme="light"] .medium-pill {
    background-color: #f4f4f5;
    color: #3f3f46;
  }

  /* Right-Side Thumbnail */
  .medium-thumb {
    width: 112px;
    height: 112px;
    border-radius: 4px;
    object-fit: cover;
    flex-shrink: 0;
    margin-top: 2px;
  }

  @media screen and (max-width: 600px) {
    .medium-body {
      gap: 16px;
    }
    .medium-title {
      font-size: 18px;
    }
    .medium-excerpt {
      display: none;
    }
    .medium-thumb {
      width: 80px;
      height: 80px;
    }
  }
</style>

<div class="medium-feed">
  <div class="medium-tabs">
    <div class="medium-tab">Latest</div>
  </div>

  {%- for post in site.posts -%}
    {%- assign words = post.content | number_of_words -%}
    {%- assign mins = words | divided_by: 200 | plus: 1 -%}
    {%- assign author_name = site.title | default: "ShortError" -%}

    <article class="medium-article">
      <div class="medium-author-row">
        <span class="medium-avatar">{{ author_name | slice: 0 }}</span>
        <span class="medium-author-name">{{ author_name }}</span>
        <span class="medium-date">· {{ post.date | date: "%b %-d, %Y" }}</span>
      </div>

      <div class="medium-body">
        <div class="medium-text">
          <h2 class="medium-title">
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
          </h2>
          <p class="medium-excerpt">
            {{ post.excerpt | strip_html | truncatewords: 30 }}
          </p>
          <div class="medium-footer">
            <span class="medium-pill">Essay</span>
            <span>{{ mins }} min read</span>
          </div>
        </div>

        <a href="{{ post.url | relative_url }}">
          <img class="medium-thumb" src="{{ post.image | default: 'https://unsplash.com' }}" alt="{{ post.title | escape }}">
        </a>
      </div>
    </article>
  {%- endfor -%}
</div>
