---
layout: default
title: "User Experience of VRChat on PC and VR Platform"
permalink: /portfolio/portfolio-2019-03-User-Experience-of-VRChat-on-PC-and-VR-Platform
excerpt: "Master degree Human Computer Interaction course group project: an empirical study<br/>"
date: 2019-03-27
collection: portfolio
toc: true
tags:
 - research
pdf: "/files/User Experience of VRChat on PC and VR Platform.pdf"
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
          {% if page.title %}<h1 class="page__title" itemprop="headline">{{ page.title | markdownify | remove: "<p>" | remove: "</p>" }}</h1>{% endif %}
          {% if page.read_time %}
            <p class="page__meta"><i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</p>
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
        {% tf _portfolio/portfolio-2019-03-User-Experience-of-VRChat-on-PC-and-VR-Platform.md %}
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