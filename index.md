markdown

---
layout: default
title: "Главная | Организация"
description: "Официальный сайт организации. Решаем сложные проблемы для более безопасного мира."
permalink: /
hero_image: /assets/images/hero-bg.jpg
hero_overlay: true
featured_projects:
  - title: "Кибербезопасность"
    description: "Разработка систем защиты от современных киберугроз"
    icon: shield
    url: /projects/cybersecurity
  - title: "Искусственный интеллект"
    description: "Исследования в области ИИ и машинного обучения"
    icon: ai
    url: /projects/ai
  - title: "Анализ данных"
    description: "Обработка и анализ больших данных для принятия решений"
    icon: data
    url: /projects/data-analysis
featured_news_count: 3
show_mission: true
show_contact_cta: true
---

<!-- Hero секция -->
<section class="hero-section" style="{% if page.hero_image %}background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('{{ page.hero_image }}');{% else %}background: linear-gradient(135deg, #0a2e4e 0%, #005b94 100%);{% endif %}">
    <div class="hero-content">
        <h1 class="hero-title">Решение проблем для более безопасного мира</h1>
        <p class="hero-subtitle">Мы объединяем экспертов для решения наиболее сложных технических и аналитических задач национального и международного масштаба</p>
        <div class="hero-actions">
            <a href="/about" class="btn btn-primary">Узнать о нас</a>
            <a href="/careers" class="btn btn-secondary">Присоединиться к нам</a>
        </div>
    </div>
</section>

<!-- Миссия -->
{% if page.show_mission %}
<section class="mission-section">
    <div class="container">
        <h2 class="section-title">Наша миссия</h2>
        <div class="mission-content">
            <p class="mission-statement">Наша организация занимается решением проблем в интересах национальной безопасности и общественного благополучия. Мы объединяем правительственные, академические и промышленные партнеров для разработки инновационных решений.</p>
            <div class="mission-values">
                <div class="value-item">
                    <div class="value-icon">🎯</div>
                    <h3 class="value-title">Целеустремленность</h3>
                    <p>Фокусируемся на решении реальных проблем</p>
                </div>
                <div class="value-item">
                    <div class="value-icon">🤝</div>
                    <h3 class="value-title">Партнерство</h3>
                    <p>Работаем в сотрудничестве с ведущими организациями</p>
                </div>
                <div class="value-item">
                    <div class="value-icon">💡</div>
                    <h3 class="value-title">Инновации</h3>
                    <p>Разрабатываем передовые технологические решения</p>
                </div>
                <div class="value-item">
                    <div class="value-icon">🌍</div>
                    <h3 class="value-title">Влияние</h3>
                    <p>Создаем положительные изменения в мире</p>
                </div>
            </div>
        </div>
    </div>
</section>
{% endif %}

<!-- Ключевые направления -->
<section class="focus-areas">
    <div class="container">
        <h2 class="section-title">Ключевые направления деятельности</h2>
        <p class="section-subtitle">Мы работаем в нескольких стратегических областях, имеющих важное значение для национальной и международной безопасности</p>

        <div class="focus-grid">
            {% for project in page.featured_projects %}
            <a href="{{ project.url }}" class="focus-card">
                <div class="focus-icon">
                    {% if project.icon == 'shield' %}
                        <svg width="48" height="48" viewBox="0 0 24 24" fill="#005b94"><path d="M12 1L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-4z"/></svg>
                    {% elsif project.icon == 'ai' %}
                        <svg width="48" height="48" viewBox="0 0 24 24" fill="#005b94"><path d="M21 11c0 5.55-3.84 10.74-9 12-5.16-1.26-9-6.45-9-12V5l9-4 9 4v6z"/></svg>
                    {% elsif project.icon == 'data' %}
                        <svg width="48" height="48" viewBox="0 0 24 24" fill="#005b94"><path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zM9 17H7v-7h2v7zm4 0h-2V7h2v10zm4 0h-2v-4h2v4z"/></svg>
                    {% endif %}
                </div>
                <h3 class="focus-title">{{ project.title }}</h3>
                <p class="focus-description">{{ project.description }}</p>
                <span class="focus-link">Подробнее →</span>
            </a>
            {% endfor %}
        </div>

        <div class="text-center">
            <a href="/projects" class="btn btn-outline">Все проекты и направления</a>
        </div>
    </div>
</section>

<!-- Последние новости -->
<section class="news-section">
    <div class="container">
        <div class="section-header">
            <h2 class="section-title">Последние новости</h2>
            <a href="/news" class="view-all">Все новости →</a>
        </div>

        <div class="news-grid">
            {% assign recent_posts = site.posts | limit: page.featured_news_count %}
            {% for post in recent_posts %}
            <article class="news-card">
                <div class="news-card-header">
                    <time class="news-date" datetime="{{ post.date | date_to_xmlschema }}">
                        {{ post.date | date: "%d.%m.%Y" }}
                    </time>
                    {% if post.categories %}
                    <span class="news-category">{{ post.categories.first }}</span>
                    {% endif %}
                </div>
                <h3 class="news-title">
                    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
                </h3>
                <p class="news-excerpt">{{ post.excerpt | strip_html | truncate: 150 }}</p>
                <a href="{{ post.url | relative_url }}" class="news-read-more">Читать далее</a>
            </article>
            {% else %}
            <p class="no-news">Новостей пока нет. Скоро появятся!</p>
            {% endfor %}
        </div>
    </div>
</section>

<!-- Вызовы и возможности -->
<section class="challenges-section">
    <div class="container">
        <h2 class="section-title">Вызовы, которые мы решаем</h2>
        <div class="challenges-content">
            <div class="challenge-item">
                <h3>Кибербезопасность</h3>
                <p>Защита критической инфраструктуры от современных киберугроз требует постоянного развития технологий и методов</p>
            </div>
            <div class="challenge-item">
                <h3>Биобезопасность</h3>
                <p>Предотвращение биологических угроз и разработка систем раннего предупреждения</p>
            </div>
            <div class="challenge-item">
                <h3>Климатическая безопасность</h3>
                <p>Анализ и смягчение последствий изменения климата для национальной безопасности</p>
            </div>
            <div class="challenge-item">
                <h3>Геополитический анализ</h3>
                <p>Прогнозирование и анализ международных конфликтов и их последствий</p>
            </div>
        </div>
    </div>
</section>

<!-- Призыв к действию (Контакты) -->
{% if page.show_contact_cta %}
<section class="cta-section">
    <div class="container">
        <h2 class="cta-title">Свяжитесь с нами</h2>
        <p class="cta-description">Заинтересованы в сотрудничестве или хотите узнать больше о нашей работе? Мы всегда открыты для диалога</p>
        <div class="cta-actions">
            <a href="/contact" class="btn btn-primary">Написать нам</a>
            <a href="mailto:info@organization.org" class="btn btn-secondary">info@organization.org</a>
        </div>
    </div>
</section>
{% endif %}
