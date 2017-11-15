---
layout: blog
---
{% assign posts = site.posts | where: 'tags', page.tag %}
{% for post in posts %}
    {% capture title %}
        {{page.tag}}
    {% endcapture %}
    {% include post-preview.md title=title post=post %}
{% endfor %}