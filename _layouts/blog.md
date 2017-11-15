{% include head.md %}

<div class="l-box blog">
    <div class="pure-g">
        <div class="l-box pure-u-1 pure-u-lg-3-4">
            {% for post in site.categories.blog %}
                {% if post.featured %}
                    <a href="{{post.url}}">
                        <div class="blog-content">
                                <div class="post-frame">
                                    <div class="pure-g">
                                        <div class="pure-u-1 pure-u-sm-2-5">
                                            <img class="pure-img-responsive" src="{{site.baseurl}}/img/blog/{{post.img}}">
                                        </div>
                                        <div class="post-excerpt pure-u-1 pure-u-sm-3-5">
                                            <h1>
                                                {{post.title}}
                                            </h1>
                                            <div class="div"></div>

                                            <p class="date">{{ post.date | date_to_long_string }}</p>

                                            {{post.excerpt}}
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </a>
                {% endif %}
            {% endfor %}
            
            {% for post in site.categories.blog %}
                <a href="{{post.url}}">
                    <div class="blog-content">
                            <div class="post-frame">
                                <div class="pure-g">
                                    <div class="pure-u-1 pure-u-sm-2-5">
                                        <img class="pure-img-responsive" src="{{site.baseurl}}/img/blog/{{post.img}}">
                                    </div>
                                    <div class="post-excerpt pure-u-1 pure-u-sm-3-5">
                                        <h1>
                                            {{post.title}}
                                        </h1>
                                        <div class="div"></div>

                                        <p class="date">{{ post.date | date_to_long_string }}</p>

                                        {{post.excerpt}}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </a>
            {% endfor %}
        </div>
        
        <div class="l-box pure-u-1 pure-u-lg-1-4">
            <div class="blog-content hidden-lg">
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