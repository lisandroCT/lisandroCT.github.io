<a href="{{include.post.url}}">
    <h1>
        {{include.post.title}} 
    </h1>
</a>
<div class="div"></div>

<p class="details">
    <span class="date"><i class="fa fa-calendar" aria-hidden="true"></i> {{include.post.date | date_to_long_string }}</span>
    {% assign tags = site.blog-tags %}
    {% unless tags.size == 0 %}
        {% for tag in tags %}
            {% if include.post.tags contains tag.tag %}
                <a href="{{site.baseurl}}{{tag.url}}">
                    <span class="tags" {% unless tag.color == null %}style="color: rgb({{tag.color}}); background: rgba({{tag.color}}, 0.2)"{% endunless %}>
                        <i class="fa fa-tag" aria-hidden="true"></i> {{tag.tag | capitalize}}
                    </span>
                </a>
            {% endif %}
        {% endfor %}
    {% endunless %}
</p>