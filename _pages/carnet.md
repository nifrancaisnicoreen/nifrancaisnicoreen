---
layout: page
title: Carnet
permalink: carnet
---

<h1>Liste Complète</h1>

<ul>
{% for post in site.posts %}
    {% if post.categories contains 'micro'%}
        {% assign shorturl = post.id | split: "/" | last %}
        <li><a href = '..{{ post.url }}'>[{{ post.date | date: "%Y-%m-%d" }}] {{ post.title }}</a></li>
    {% endif %}
{% endfor %}
</ul>


{% for post in site.posts %}
    {% if post.categories contains 'micro'%}
<hr class = "bits-hr">
<div class = "bits">
<h1 class = "title">{{ post.title }}</h1>
<div>
<p class = "date">{{ post.date | date: "%B %e, %Y" }}</p>
<div class="tags">
{% for category in post.categories %}
<a href="{{site.baseurl}}/categories/#{{category|slugize}}">{{category}}</a>
{% unless forloop.last %}&nbsp;{% endunless %}
{% endfor %}
</div>
</div>
{{ post.content }}
</div>
    {% endif %}
{% endfor %}

