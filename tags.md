---
title: 태그
layout: "page"
icon: fa-tag
order: 4
description: 태그 별로 글을 정리하여 보여주는 페이지입니다.
---
<div class="tag-cloud">
{% for tag in site.tags %}
  <span>
    <a href="#{{ tag | first | slugize }}">
      {{ tag | first }}
    </a> &nbsp;
  </span>
{% endfor %}
</div>
<hr>
<div class="archives">
{% for tag in site.tags %}
  <div class="archive-group">
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
    <h3 id="#{{ tag_name | slugize }}">{{ tag_name }}</h3>
    <a name="{{ tag_name | slugize }}"></a>
    {% for post in site.tags[tag_name] %}
    <div class="archive-item">
      <h4><a href="{{ root_url }}{{ post.url }}">{{ post.title }}</a></h4>
    </div>
    {% endfor %}
  </div>
{% endfor %}
</div>
