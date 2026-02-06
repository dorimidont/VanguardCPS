markdown
---
layout: page
title: "Главная"
---

# Сообщество кибербезопасности

Открытое сообщество исследователей и специалистов по информационной безопасности.

## Последние публикации

{% assign recent_posts = site.posts | sort: 'date' | reverse %}
{% for post in recent_posts limit: 3 %}
- [{{ post.title }}]({{ post.url }}) *({{ post.date | date: "%d.%m.%Y" }})*
{% endfor %}

## Активные проекты

{% for project in site.data.projects limit: 3 %}
- **{{ project.title }}** - {{ project.description }}
{% endfor %}

---

[Все посты](/posts) | [Все проекты](/projects)
