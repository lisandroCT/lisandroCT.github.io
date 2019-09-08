{% assign post = include.post %}

{% assign tagsCount = 0 %}
{% assign red = 0 %}
{% assign green = 0 %}
{% assign blue = 0 %}

{% unless site.blog-tags == null %}
    {% unless site.blog-tags.size == 0 %}
        {% for tag in site.blog-tags %}
            {% if post.tags contains tag.slug %}
                {% assign tagsCount = tagsCount | plus: 1 %}

                {% assign red = red | plus: tag.red %}
                {% assign green = green | plus: tag.green %}
                {% assign blue = blue | plus: tag.blue %}
            {% endif %}
        {% endfor %}

        {% if tagsCount > 0 %}
            {% assign red = red | divided_by: tagsCount %}
            {% assign green = green | divided_by: tagsCount %}
            {% assign blue = blue | divided_by: tagsCount %}
        {% endif %}
    {% endunless %}
{% endunless %}

{{red}}, {{green}}, {{blue}}