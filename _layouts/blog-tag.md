---
layout: blog
---
{% assign posts = site.posts | where: 'tags', page.slug %}
{% for post in posts %}
    {% capture title %}
        {{page.display}}
    {% endcapture %}
    {% include post-preview.md title=title post=post %}
{% endfor %}