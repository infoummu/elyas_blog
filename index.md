---
layout: default
title: Home
pagination:
  enabled: true
  per_page: 3
  sort_field: 'date'
  sort_reverse: true
---

<h2>Halaman Index New :</h2>  

<ul>
    {% for post in paginator.posts %}
      <li>
          <h2><a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">{{ post.title }}</a></h2>
           <time datetime="{{ post.date | date_to_xmlschema }}" class="by-line">  <i>{{ post.date | date_to_string }}</i> | {{post.author}} </time> 
          <p>{{ post.description| strip_html | truncatewords:40 }}</p>
      </li>
    {% endfor %}
</ul>
