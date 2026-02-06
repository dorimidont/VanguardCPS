---
layout: page
title: "Наши проекты"
---

# Наши проекты

{% for project in site.data.projects %}
## {{ project.title }}

**Статус:** {{ project.status }}

{{ project.description }}

**Технологии:** {{ project.technologies | join: ", " }}

{% if project.url %}
[Ссылка на проект]({{ project.url }})
{% endif %}

---
