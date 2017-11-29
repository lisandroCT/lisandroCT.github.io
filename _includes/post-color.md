{% assign post = include.post %}

{% assign siteTags = site.blog-tags %}
{% assign tagsCount = 0 %}
{% assign red = 0 %}
{% assign green = 0 %}
{% assign blue = 0 %}

{% unless siteTags == null %}
    {% unless siteTags.size == 0 %}
        {% for tag in siteTags %}
            {% if post.tags contains tag.tag %}
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