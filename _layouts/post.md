{% include head.md %}

<div class="l-box blog">
    <div class="pure-g">
        <div class="l-box pure-u-1 pure-u-lg-3-4">
            <div class="blog-content">
                <div class="post-frame">
                    <h1>
                        {{page.title}}
                    </h1>
                    <div class="div"></div>

                    <p class="date">{{ page.date | date_to_long_string }}</p>

                    <img class="pure-img-responsive" src="{{site.baseurl}}/img/blog/{{page.img}}">
                    
                    {{page.content}}
                </div>
            </div>
        </div>
        
        <div class="l-box pure-u-1 pure-u-lg-1-4 hidden-lg">
            <div class="blog-content">
                <h1>RECENT POSTS</h1>

                {% for post in site.categories.blog %}
                <a href="{{post.url}}">
                    <div class="frame">
                        <img class="pure-img-responsive" src="{{site.baseurl}}/img/blog/{{post.img}}">
                        <h2>
                            {{post.title}}
                        </h2>
                    </div>
                    </a>
                {% endfor %}
            </div>
            
            {% assign tags = site.tags %}
            {% unless tags.size == 0 %}
                <div class="blog-content">
                    <h1>CATEGORIES</h1>
                    <ul class="tags-list">
                        {% for tag in site.tags %}
                            <li><a href="">
                                {{tag[0] | capitalize}}
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