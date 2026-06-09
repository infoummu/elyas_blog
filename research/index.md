---
layout: default
title: Research
pagination:
  enabled: true
  category: research
  per_page: 3
  permalink: '/research/:num/'
  sort_field: 'date'
  sort_reverse: true
---

<article>
<h2>Research</h2>
<p>Semua postingan dengan kategori <strong>research</strong>:</p>
<ul>
    {% for post in paginator.posts %}
      <li>
          <h2><a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">{{ post.title }}</a></h2>
          <time datetime="{{ post.date | date_to_xmlschema }}" class="by-line">
              <i>{{ post.date | date_to_string }}</i> | {{ post.author }}
          </time>
          <p>{{ post.description | strip_html | truncatewords:40 }}</p>
      </li>
    {% endfor %}
</ul>
</article>
