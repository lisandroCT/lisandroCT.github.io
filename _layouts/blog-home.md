---
layout: blog
---
{% assign featured_posts = site.categories.blog | where: 'featured', true %}
{% for post in featured_posts %}
    {% include post-preview.md title='featured post' post=post %}
{% endfor %}

{% for post in site.categories.blog %}
    {% include post-preview.md post=post %}
{% endfor %}