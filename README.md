# Srini's pages

Srinivasan Ravichandran's personal pages. A "diary" or blog of my personal and professional journey, with a focus on AI, ML, and related technologies.

{% for post in site.posts limit: 5 %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  <p>{{ post.excerpt }}</p>
{% endfor %}