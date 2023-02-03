---
layout: default
title: titles.portfolios.Comparison-of-Tablet-based-AR-and-Tablet-App-in-Veterinary-Self-learning
title_code: Comparison-of-Tablet-based-AR-and-Tablet-App-in-Veterinary-Self-learning
permalink: /portfolio/portfolio-2021-03-Comparison-of-Tablet-based-AR-and-Tablet-App-in-Veterinary-Self-learning
excerpt: portfolios_excerpt.Comparison-of-Tablet-based-AR-and-Tablet-App-in-Veterinary-Self-learning
date: 2021-03-27
collection: portfolio
published: /publication/2021-07-14-Augmented-Reality-for-Veterinary-self-learning-during-the-pandemic-a-holistic-study-protocol-for-a-remote-randomised-cross-over-study
tags:
 - published
 - Android
 - iOS
 - Unity
image: VetAR2021.png
video: "https://youtu.be/xElDW8IZKPA"
b_video: "https://www.bilibili.com/video/BV19d4y1H7BD/"
---

{% include base_path %}

{% if page.header.overlay_color or page.header.overlay_image or page.header.image %}
  {% include page__hero.html %}
{% endif %}

{% if page.url != "/" and site.breadcrumbs %}
  {% unless paginator %}
    {% include breadcrumbs.html %}
  {% endunless %}
{% endif %}

<div id="main" role="main">
  {% include sidebar.html %}

  <article class="page" itemscope itemtype="http://schema.org/CreativeWork">
    {% if page.title %}<meta itemprop="headline" content="{{ page.title | markdownify | strip_html | strip_newlines | escape_once }}">{% endif %}
    {% if page.excerpt %}<meta itemprop="description" content="{{ page.excerpt | markdownify | strip_html | strip_newlines | escape_once }}">{% endif %}
    {% if page.date %}<meta itemprop="datePublished" content="{{ page.date | date: "%B %d, %Y" }}">{% endif %}
    {% if page.modified %}<meta itemprop="dateModified" content="{{ page.modified | date: "%B %d, %Y" }}">{% endif %}

    <div class="page__inner-wrap">
      {% unless page.header.overlay_color or page.header.overlay_image %}
        <header>
          {% if page.title %}<h1 class="page__title" itemprop="headline">{% t page.title %}</h1>{% endif %}
          {% if page.read_time %}
            <p class="page__meta"><i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</p>
          {% endif %}

          {% if page.date %}
            <p class="page__date"><strong><i class="fa fa-fw fa-calendar" aria-hidden="true"></i> {{ site.translations[site.lang].UI.date_label | default: "Published:" }}</strong> <time datetime="{{ page.date | date_to_xmlschema }}">{{ page.date | default: "1900-01-01" | date: "%B %d, %Y" }}</time>
              {% if page.published %}
                <a href="{{ base_path }}{{page.published}}">({% t publication.published%})</a>
              {% endif %}
            </p>
          {% endif %}
        </header>
      {% endunless %}

      <section class="page__content" itemprop="text">
        {% if page.toc %}
          <aside class="sidebar__right {% if page.toc_sticky %}sticky{% endif %}">
            <nav class="toc">
              <header><h4 class="nav__title"><i class="fas fa-{{ page.toc_icon | default: 'align-justify' }}"></i> {{ page.toc_label | default: site.translations[site.lang].UI.toc_label | default: "On this page" }}</h4></header>
              {% include toc.html sanitize=true html=content h_min=1 h_max=6 class="toc__menu" %}
            </nav>
          </aside>
        {% endif %}
        {% tf _portfolio/portfolio-2021-03-Comparison-of-Tablet-based-AR-and-Tablet-App-in-Veterinary-Self-learning.md %}
        {% if page.link %}<div><a href="{{ page.link }}" class="btn">{{ site.translations[site.lang].UI.ext_link_label | default: "Direct Link" }}</a></div>{% endif %}
      </section>

      <footer class="page__meta">
        {% if site.translations[site.lang].UI.meta_label %}
          <h4 class="page__meta-title">{{ site.translations[site.lang].UI.meta_label }}</h4>
        {% endif %}
        {% include page__taxonomy.html %}
      </footer>

      {% if page.share %}{% include social-share.html %}{% endif %}

      {% include post_pagination.html %}
    </div>

    {% if site.comments.provider and page.comments %}
      {% include comments.html %}
    {% endif %}
  </article>

  {% comment %}<!-- only show related on a post page when not disabled -->{% endcomment %}
  {% if page.id and page.related and site.related_posts.size > 0 %}
    <div class="page__related">
      {% if site.translations[site.lang].UI.related_label %}
        <h4 class="page__related-title">{{ site.translations[site.lang].UI.related_label | default: "You May Also Enjoy" }}</h4>
      {% endif %}
      <div class="grid__wrapper">
        {% for post in site.related_posts limit:3 %}
          {% include archive-single.html type="grid" %}
        {% endfor %}
      </div>
    </div>
  {% endif %}
</div>
