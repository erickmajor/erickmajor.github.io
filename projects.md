---
layout: project
title: Projects
description: Some description.
permalink: /projects/
---

<main class="home" id="projects" role="projects" itemprop="mainContentOfPage" itemscope="itemscope" itemtype="http://schema.org/Blog">
    <div id="grid" class="row flex-grid">
    {% for project in site.projects %}
        <article class="box-item" itemscope="itemscope" itemtype="http://schema.org/BlogPosting" itemprop="blogPost">
            <div class="box-body">
                {% if project.image %}
                    <div class="cover">
                        {% include new-project-tag.html date=project.date %}
                        <a href="{{ project.url | prepend: site.baseurl }}" {%if isnewpost %}class="new-project"{% endif %}>
                            <img src="assets/img/placeholder.png" data-url="{{ project.image }}" class="preload">
                        </a>
                    </div>
                {% endif %}
                <div class="box-info">
                    <meta itemprop="datePublished" content="{{ project.date | date_to_xmlschema }}">
                    <time itemprop="datePublished" datetime="{{ project.date | date_to_xmlschema }}" class="date">
                        {% include date.html date=project.date %}
                    </time>
                    <a class="project-link" href="{{ project.url | prepend: site.baseurl }}">
                        <h2 class="project-title" itemprop="name">
                            {{ project.title }}
                        </h2>
                    </a>
                    <a class="project-link" href="{{ project.url | prepend: site.baseurl }}">
                        <p class="description">{{ project.introduction }}</p>
                    </a>
                    <div class="tags">
                        {% for tag in project.tags %}
                            <a href="{{ site.baseurl}}/tags/#{{tag | slugify }}">{{ tag }}</a>
                        {% endfor %}
                    </div>
                </div>
            </div>
        </article>
    {% endfor %}
    </div>
</main>