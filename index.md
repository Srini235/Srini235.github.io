---
layout: home
title: "Srini's Pages"
description: >-
  A diary of my personal and professional journey — focused on AI, ML,
  and the tools I build or break along the way.
author: Srini
---

## Welcome

I'm **Srinivasan Ravichandran**. This site is a running diary of what I'm
learning, building, and breaking — with most posts grounded in **AI, machine
learning**, and the developer tooling that surrounds them.

It exists for three reasons:

- **To think in writing.** Drafting forces clarity; clarity compounds.
- **To leave a trail.** Future-me will want to know why a decision was made.
- **To share.** If a post saves you an afternoon, the trail served its purpose.

## Recent posts

<ul class="post-list">
  {% for post in site.posts limit: 5 %}
    <li>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="post-meta">
        <time datetime="{{ post.date | date_to_xmlschema }}">
          {{ post.date | date: "%B %-d, %Y" }}
        </time>
      </p>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>

<p><a href="{{ '/2026/' | relative_url }}">Browse the full archive →</a></p>
