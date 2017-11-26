---
layout: blog
---
{% unless site.categories.blog == null %}
    {% assign featured_posts = site.categories.blog | where: 'featured', true | sort:'date' %}
    {% for post in featured_posts %}
        {% include post-preview.md title='featured post' post=post %}
    {% endfor %}
    
    {% assign last_posts = site.categories.blog | sort:'date' %}
    {% for post in site.categories.blog %}
        {% include post-preview.md post=post %}
    {% endfor %}
{% endunless %}