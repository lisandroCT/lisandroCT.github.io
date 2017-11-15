{% include head.md %}

<div class="l-box blog">
    <div class="pure-g">
        <div class="l-box pure-u-1 pure-u-lg-3-4">
            {% for post in site.categories.blog %}
                {% if post.featured %}
                    <div class="blog-content">
                        <h1>
                            FEATURED POST
                        </h1>

                        <div class="post-frame">
                            <h1>
                                <a href="{{post.url}}">{{post.title}}</a>
                            </h1>
                            <div class="div"></div>

                            <p class="date">{{ post.date | date_to_long_string }}</p>

                            {{post.excerpt}}
                        </div>
                    </div>
                {% endif %}
            {% endfor %}
            
            {% for post in site.categories.blog %}
                <div class="blog-content">
                    <div class="post-frame">
                        <div class="pure-g">
                            <div class="pure-u-1 pure-u-sm-2-5">
                                <img class="pure-img-responsive" src="{{site.baseurl}}/img/blog/{{post.img}}">
                            </div>
                            <div class="post-excerpt pure-u-1 pure-u-sm-3-5">
                                <h1>
                                    <a href="{{post.url}}">{{post.title}}</a>
                                </h1>
                                <div class="div"></div>

                                <p class="date">{{ post.date | date_to_long_string }}</p>

                                {{post.excerpt}}
                            </div>
                        </div>
                    </div>
                </div>
            {% endfor %}
        </div>
        
        <div class="l-box pure-u-1 pure-u-lg-1-4">
            <div class="blog-content hidden-lg">
                <h1>RECENT POSTS</h1>

                {% for post in site.categories.blog %}
                    <div class="frame">
                        <img class="pure-img-responsive" src="{{site.baseurl}}/img/blog/{{post.img}}">
                        <h2>
                            <a href="{{post.url}}">{{post.title}}</a>
                        </h2>
                    </div>
                {% endfor %}
            </div>
            
            <div class="blog-content">
                <h1>CATEGORIES</h1>

                {% for post in site.categories.blog %}
                    <h2>
                        <a href="{{post.url}}">{{post.title}}</a>
                    </h2>
                {% endfor %}
            </div>
        </div>
    </div>
</div>

<div class="blog-social">
    {% include social.md %}
</div>
    
{% include foot.md %}