markdown
---
layout: page
title: "Посты и публикации"
---

# Посты и публикации

{% assign sorted_posts = site.posts | sort: 'date' | reverse %}

{% for post in sorted_posts %}
## [{{ post.title }}]({{ post.url }})
*{{ post.date | date: "%d.%m.%Y" }}*

{{ post.excerpt }}

{% if post.tags %}
Теги: {% for tag in post.tags %}`{{ tag }}`{% unless forloop.last %}, {% endunless %}{% endfor %}
{% endif %}

---
{% endfor %}
