<a href="{{include.post.url}}">
    <h1>
        {{include.post.title}} 
    </h1>
</a>
<div class="div"></div>

<p class="details">
    <span class="time"><i class="fa fa-clock-o" aria-hidden="true"></i> {{include.post.date | date: "%I:%M %p" }}</span>
    <span class="date"><i class="fa fa-calendar" aria-hidden="true"></i> {{include.post.date | date_to_long_string }}</span>
    
    {% assign comments = site.data.comments[include.post.slug] %}
    {% unless comments == null or comments.size == 0 %}
        <span class="comments-count"><i class="fa fa-comments" aria-hidden="true"></i> {{comments.size}} comments</span>
    {% endunless %}
    
    {% unless site.blog-tags == null %}
        {% unless site.blog-tags.size == 0 %}
            {% for tag in site.blog-tags %}
                {% if post.tags contains tag.slug %}
                    {% assign red = tag.red %}
                    {% assign green = tag.green %}
                    {% assign blue = tag.blue %}
                    
                    <a href="{{site.baseurl}}{{tag.url}}">
                        <span class="tags" style="border-left: 0.3em solid rgb({{red}}, {{green}}, {{blue}}); background: rgba({{red}}, {{green}}, {{blue}}, 0.2);">
                            <i class="fa fa-tag" aria-hidden="true" style="color: rgb({{red}}, {{green}}, {{blue}})"></i> {{tag.display}}
                        </span>
                    </a>
                {% endif %}
            {% endfor %}
        {% endunless %}
    {% endunless %}
</p>