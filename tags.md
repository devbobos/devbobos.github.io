---
title: 태그
layout: "page"
icon: fa-tag
order: 4
---

<div class="tag-cloud">
{% for tag in site.tags %}
  <span>
    <a href="#{{ tag | first | slugize }}">
      {{ tag | first }}
    </a> &nbsp;&nbsp;
  </span>
{% endfor %}
</div>

<div id="archives">
{% for tag in site.tags %}
  <div class="archive-group">
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
    <h3 id="#{{ tag_name | slugize }}">{{ tag_name }}</h3>
    <a name="{{ tag_name | slugize }}"></a>
    {% for post in site.tags[tag_name] %}
    <div class="archive-item">
      <span class="icon {{ _post.icon }}">
        <h4><a href="{{ root_url }}{{ post.url }}">{{ post.title }}</a></h4>
      </span>
    </div>
    {% endfor %}
  </div>
{% endfor %}
</div>
