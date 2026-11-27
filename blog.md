---
layout: page
permalink: /blog/
---

<style>
  /* Hide Minima's default page title */
  .post-header {
    display: none;
  }

  .clean-feed {
    max-width: 720px;
    margin: 0 auto;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
  }

  .feed-item {
    padding: 28px 0;
    border-bottom: 1px solid #27272a;
  }

  html[data-theme="light"] .feed-item {
    border-bottom-color: #e4e4e7;
  }

  /* Top Date Row with Calendar Icon */
  .feed-date-row {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    font-size: 13px;
    color: #a1a1aa;
    margin-bottom: 10px;
  }

  html[data-theme="light"] .feed-date-row {
    color: #71717a;
  }

  .feed-date-row svg {
    flex-shrink: 0;
    opacity: 0.85;
  }

  /* Content + Optional Right Thumbnail Split */
  .feed-body {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 32px;
  }

  .feed-text {
    flex: 1;
    min-width: 0;
  }

  .feed-title {
    font-size: 22px;
    font-weight: 700;
    line-height: 1.3;
    letter-spacing: -0.015em;
    margin: 0 0 8px 0 !important;
  }

  .feed-title a {
    color: #f4f4f5 !important;
    text-decoration: none;
  }

  .feed-title a:hover {
    opacity: 0.82;
  }

  html[data-theme="light"] .feed-title a {
    color: #18181b !important;
  }

  .feed-excerpt {
    font-size: 15.5px;
    line-height: 1.55;
    color: #a1a1aa;
    margin: 0;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  html[data-theme="light"] .feed-excerpt {
    color: #52525b;
  }

  /* Optional Right-Side Rectangular Image (Only renders if image exists) */
  .feed-thumb {
    width: 160px;
    height: 106px;
    border-radius: 4px;
    object-fit: cover;
    flex-shrink: 0;
    margin-top: 2px;
  }

  @media screen and (max-width: 600px) {
    .feed-body {
      gap: 16px;
    }
    .feed-title {
      font-size: 18px;
    }
    .feed-thumb {
      width: 100px;
      height: 70px;
    }
  }
</style>

<div class="clean-feed">
  {%- for post in site.posts -%}
    {%- assign day = post.date | date: "%-d" -%}
    {%- case day -%}
      {%- when '1' or '21' or '31' -%}{%- assign suffix = "st" -%}
      {%- when '2' or '22' -%}{%- assign suffix = "nd" -%}
      {%- when '3' or '23' -%}{%- assign suffix = "rd" -%}
      {%- else -%}{%- assign suffix = "th" -%}
    {%- endcase -%}

    {%- comment -%} Use front-matter image if set, otherwise auto-detect the first image inside the post content {%- endcomment -%}
    {%- assign post_img = post.image -%}
    {%- unless post_img -%}
      {%- if post.content contains '<img ' -%}
        {%- assign img_parts = post.content | split: 'src="' -%}
        {%- if img_parts.size > 1 -%}
          {%- assign post_img = img_parts[1] | split: '"' | first -%}
        {%- endif -%}
      {%- endif -%}
    {%- endunless -%}

    <article class="feed-item">
      <div class="feed-date-row">
        <svg viewBox="0 0 24 24" width="14" height="14" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect>
          <line x1="16" y1="2" x2="16" y2="6"></line>
          <line x1="8" y1="2" x2="8" y2="6"></line>
          <line x1="3" y1="10" x2="21" y2="10"></line>
        </svg>
        <span>{{ post.date | date: "%B" }} {{ day }}{{ suffix }}, {{ post.date | date: "%Y" }}</span>
      </div>

      <div class="feed-body">
        <div class="feed-text">
          <h2 class="feed-title">
            <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
          </h2>
          <p class="feed-excerpt">
            {{ post.excerpt | strip_html | truncatewords: 28 }}
          </p>
        </div>

        {%- if post_img and post_img != "" -%}
          <a href="{{ post.url | relative_url }}">
            <img class="feed-thumb" src="{{ post_img }}" alt="{{ post.title | escape }}">
          </a>
        {%- endif -%}
      </div>
    </article>
  {%- endfor -%}
</div>
