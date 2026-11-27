---
layout: page
permalink: /blog/
---

<style>
  /* Hide Minima's default web header */
  .post-header {
    display: none;
  }

  /* Broadsheet Paper Sheet */
  .print-paper {
    font-family: "Times New Roman", Times, Georgia, serif;
    padding: 28px 32px;
    border: 1px solid #3f3f46;
    /* Dark Newsprint */
    background-color: #181817;
    background-image: radial-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 0);
    background-size: 16px 16px;
    color: #e2dfd7;
    box-shadow: 0 8px 30px rgba(0, 0, 0, 0.45);
  }

  /* Classic Aged Newsprint Paper in Light Mode */
  html[data-theme="light"] .print-paper {
    background-color: #f4efe6;
    background-image: radial-gradient(rgba(0, 0, 0, 0.04) 1px, transparent 0);
    background-size: 14px 14px;
    color: #1c1917;
    border-color: #c7bfb0;
    box-shadow: 0 6px 24px rgba(0, 0, 0, 0.12);
  }

  /* Top Ears + Masthead */
  .print-top-row {
    display: grid;
    grid-template-columns: 110px 1fr 110px;
    align-items: center;
    gap: 12px;
    margin-bottom: 10px;
  }

  .print-ear {
    border: 1px solid currentColor;
    padding: 6px 8px;
    font-size: 10px;
    line-height: 1.3;
    text-align: center;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .print-masthead {
    text-align: center;
    font-size: 44px;
    font-weight: 700;
    letter-spacing: 0.04em;
    line-height: 1;
    margin: 0 !important;
    text-transform: uppercase;
    font-family: Georgia, "Times New Roman", serif;
  }

  /* Double Rule Dateline Bar */
  .print-dateline {
    display: flex;
    justify-content: space-between;
    border-top: 2px solid currentColor;
    border-bottom: 4px double currentColor;
    padding: 5px 4px;
    margin-bottom: 20px;
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.08em;
  }

  /* Lead Headline Banner */
  .print-headline-block {
    text-align: center;
    border-bottom: 1px solid currentColor;
    padding-bottom: 14px;
    margin-bottom: 18px;
  }

  .print-headline {
    font-size: 32px;
    font-weight: 700;
    line-height: 1.15;
    margin: 0 0 8px 0 !important;
    letter-spacing: -0.01em;
  }

  .print-headline a {
    color: inherit !important;
    text-decoration: none;
  }

  .print-headline a:hover {
    text-decoration: underline;
  }

  .print-subhead {
    font-style: italic;
    font-size: 16px;
    opacity: 0.85;
    margin: 0 0 8px 0;
  }

  .print-byline {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.12em;
    font-weight: 700;
  }

  /* True Multi-Column Newspaper Body (with vertical column rules) */
  .print-lead-columns {
    column-count: 3;
    column-gap: 22px;
    column-rule: 1px solid rgba(160, 155, 145, 0.35);
    text-align: justify;
    font-size: 14.5px;
    line-height: 1.55;
    padding-bottom: 20px;
    border-bottom: 3px double currentColor;
    margin-bottom: 22px;
  }

  html[data-theme="light"] .print-lead-columns {
    column-rule-color: rgba(28, 25, 23, 0.3);
  }

  .print-lead-columns p {
    margin-bottom: 12px;
  }

  /* Classic Newspaper Drop Cap */
  .print-lead-columns p:first-of-type::first-letter {
    float: left;
    font-size: 46px;
    line-height: 0.85;
    padding-top: 4px;
    padding-right: 8px;
    padding-bottom: 2px;
    font-weight: 700;
  }

  /* Halftone Black-and-White Newspaper Photo */
  .print-photo-box {
    break-inside: avoid;
    margin-bottom: 12px;
    border: 1px solid currentColor;
    padding: 4px;
  }

  .print-photo-box img {
    width: 100%;
    height: 140px;
    object-fit: cover;
    display: block;
    filter: grayscale(100%) contrast(1.2);
  }

  .print-photo-caption {
    font-size: 11px;
    font-style: italic;
    line-height: 1.3;
    padding-top: 4px;
    text-align: left;
  }

  .print-jump-link {
    display: inline-block;
    font-size: 11px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: inherit !important;
    text-decoration: underline;
    margin-top: 4px;
  }

  /* Lower Broadsheet Columns for Other Editions */
  .print-archive-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
  }

  .print-brief {
    border-bottom: 1px solid rgba(160, 155, 145, 0.35);
    padding-bottom: 14px;
    text-align: justify;
  }

  html[data-theme="light"] .print-brief {
    border-bottom-color: rgba(28, 25, 23, 0.3);
  }

  .print-brief:nth-child(odd) {
    padding-right: 18px;
    border-right: 1px solid rgba(160, 155, 145, 0.35);
  }

  html[data-theme="light"] .print-brief:nth-child(odd) {
    border-right-color: rgba(28, 25, 23, 0.3);
  }

  .print-brief-title {
    font-size: 18px;
    font-weight: 700;
    line-height: 1.2;
    text-align: left;
    margin: 0 0 6px 0 !important;
  }

  .print-brief-title a {
    color: inherit !important;
    text-decoration: none;
  }

  .print-brief-title a:hover {
    text-decoration: underline;
  }

  .print-brief-meta {
    font-size: 10px;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    margin-bottom: 6px;
    opacity: 0.8;
  }

  .print-brief-text {
    font-size: 13.5px;
    line-height: 1.5;
    margin-bottom: 6px;
  }

  @media screen and (max-width: 700px) {
    .print-paper {
      padding: 18px 16px;
    }
    .print-top-row {
      grid-template-columns: 1fr;
    }
    .print-ear {
      display: none;
    }
    .print-masthead {
      font-size: 30px;
    }
    .print-lead-columns {
      column-count: 1;
    }
    .print-archive-grid {
      grid-template-columns: 1fr;
    }
    .print-brief:nth-child(odd) {
      padding-right: 0;
      border-right: none;
    }
  }
</style>

<div class="print-paper">
  <!-- Classic Newspaper Header with Corner "Ears" -->
  <div class="print-top-row">
    <div class="print-ear">Morning Edition<br>Est. 2026</div>
    <h1 class="print-masthead">The Daily Gazette</h1>
    <div class="print-ear">Price: Free<br>All Pages</div>
  </div>

  <!-- Double-Rule Dateline -->
  <div class="print-dateline">
    <span>Vol. I — No. {{ site.posts.size }}</span>
    <span>{{ "now" | date: "%A, %B %-d, %Y" }}</span>
    <span>Personal Print</span>
  </div>

  {%- for post in site.posts -%}
    {%- if forloop.first -%}
      <!-- Front-Page Lead Headline -->
      <div class="print-headline-block">
        <h2 class="print-headline">
          <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </h2>
        <div class="print-byline">
          By {{ site.title | default: "The Editor" }} &nbsp;•&nbsp; {{ post.date | date: "%B %-d, %Y" }}
        </div>
      </div>

      <!-- 3-Column Justified Print Text with Drop Cap & B&W Photo -->
      <div class="print-lead-columns">
        <p>{{ post.content | strip_html | truncatewords: 165 }}</p>

        <div class="print-photo-box">
          <img src="https://unsplash.com" alt="Editorial illustration">
          <div class="print-photo-caption">Fig. 1 — Morning reflections over a quiet cup of tea.</div>
        </div>

        <a class="print-jump-link" href="{{ post.url | relative_url }}">Continued on Page A2 →</a>
      </div>

      {%- if site.posts.size > 1 -%}
        <div class="print-archive-grid">
      {%- endif -%}
    {%- else -%}
      <!-- Secondary Broadsheet Columns -->
      <article class="print-brief">
        <div class="print-brief-meta">{{ post.date | date: "%B %-d, %Y" }}</div>
        <h3 class="print-brief-title">
          <a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </h3>
        <p class="print-brief-text">{{ post.excerpt | strip_html | truncatewords: 35 }}</p>
        <a class="print-jump-link" href="{{ post.url | relative_url }}">Read Full Dispatch →</a>
      </article>
    {%- endif -%}

    {%- if forloop.last and site.posts.size > 1 -%}
      </div>
    {%- endif -%}
  {%- endfor -%}
</div>
