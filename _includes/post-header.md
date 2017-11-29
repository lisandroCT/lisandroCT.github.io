{% assign siteTags = site.blog-tags %}
{% assign tags = "" | split: ", " %}
{% unless siteTags == null %}
    {% unless siteTags.size == 0 %}
        {% for tag in siteTags %}
            {% if include.post.tags contains tag.tag %}
                {% assign index = forloop.index0 | split: ", " %}
                {% assign tags = tags | concat: index %}
            {% endif %}
        {% endfor %}
    {% endunless %}
{% endunless %}

<!--
<a href="{{post.url}}">
    {% unless tags.size == 0 %}
        {% assign red = 0 %}
        {% assign green = 0 %}
        {% assign blue = 0 %}
    
        {% for tag in tags %}
            {% assign i = tag | times: 1 %}
            
            {% assign red = red | plus: siteTags[i].red %}
            {% assign green = green | plus: siteTags[i].green %}
            {% assign blue = blue | plus: siteTags[i].blue %}
        {% endfor %}
        
        {% assign red = red | divided_by: tags.size %}
        {% assign green = green | divided_by: tags.size %}
        {% assign blue = blue | divided_by: tags.size %}
    {% endunless %}
    
    <div class="cover snippet" {% unless tags.size == 0 %}style="border-left: 0.3em solid rgb({{red}}, {{green}}, {{blue}}); background: rgba({{red}}, {{green}}, {{blue}}, 0.4);"{% endunless %}>
        {% highlight none %}{{include.post.snippet}}{% endhighlight %}
    </div>
</a>
-->

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
    
    {% unless tags.size == 0 %}
        {% for tag in tags %}
            {% assign i = tag | times: 1 %}
            
            {% assign red = siteTags[i].red %}
            {% assign green = siteTags[i].green %}
            {% assign blue = siteTags[i].blue %}
            
            <a href="{{site.baseurl}}{{tag.url}}">
                <span class="tags" style="border-left: 0.3em solid rgb({{red}}, {{green}}, {{blue}}); background: rgba({{red}}, {{green}}, {{blue}}, 0.2);">
                    <i class="fa fa-tag" aria-hidden="true" style="color: rgb({{red}}, {{green}}, {{blue}})"></i> {{siteTags[i].tag | capitalize}}
                </span>
            </a>
        {% endfor %}
    {% endunless %}
</p>