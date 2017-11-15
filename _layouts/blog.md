{% include head.md %}

<div class="l-box blog">
    <div class="pure-g">
        <div class="l-box pure-u-1 pure-u-lg-3-4">
            {{content}}
        </div>
        
        <div class="l-box pure-u-1 pure-u-lg-1-4">
            <div class="blog-content hidden-xs">
                <h1>Last Posts</h1>
                
                <div class=pure-g>
                    {% for post in site.categories.blog %}
                        <div class="pure-u-1 pure-u-sm-1-2 pure-u-md-1-3 pure-u-lg-1">
                            <div class="frame">
                                    <a href="{{post.url}}">
                                        <img class="pure-img-responsive" src="{{site.baseurl}}/img/blog/{{post.img}}">
                                    </a>
                                    <a href="{{post.url}}">
                                        <h2>
                                            {{post.title}}
                                        </h2>
                                    </a>
                            </div>
                        </div>
                    {% endfor %}
                </div>
            </div>
            
            {% assign tags = site.blog-tags %}
            {% unless tags.size == 0 %}
                <div class="blog-content">
                    <h1>Tags</h1>
                    <ul class="tags-list">
                        {% for tag in tags %}
                            <li><a href="{{site.baseurl}}{{tag.url}}">
                                {{tag.tag | capitalize}}
                            </a></li>
                        {% endfor %}
                    </ul>
                </div>
            {% endunless %}
        </div>
    </div>
</div>

<div class="blog-social">
    {% include social.md %}
</div>
    
{% include foot.md %}