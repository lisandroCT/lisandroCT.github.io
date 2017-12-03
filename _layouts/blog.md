{% include head.md %}

<div class="l-box blog">
    <div class="pure-g">
        <div class="l-box pure-u-1 pure-u-lg-3-4">
            {{content}}
        </div>
        
        <div class="l-box pure-u-1 pure-u-lg-1-4">
            {% unless site.categories.blog == null %}
                {% assign ordered_posts = site.categories.blog | sort:'date' | reverse %}
                {% unless ordered_posts.size == 0 %}
                    <div class="blog-content hidden-xs">
                        <h1>Last Posts</h1>

                        <div class=pure-g>
                            {% for post in ordered_posts %}                                
                                <div class="pure-u-1 pure-u-sm-1-3 pure-u-lg-1">
                                    <a href="{{post.url}}">
                                        <div style="padding: 0.2em; height: 100%;">
                                            <div class="small-thumbnail snippet" style="border-left: 0.3em solid rgb({% include post-color.md post=post %}); background: rgba({% include post-color.md post=post %}, 0.2);">
                                                <h2>
                                                    {{post.title}}
                                                </h2>
                                            </div>
                                        </div>
                                    </a>
                                </div>
                            {% endfor %}
                        </div>
                    </div>
                {% endunless %}
            {% endunless %}
            
            {% unless site.blog-tags == null %}
                {% unless site.blog-tags.size == 0 %}
                    <div class="blog-content">
                        <h1>Tags</h1>
                        <ul class="tags-list">
                            {% for tag in site.blog-tags %}
                                {% assign posts = site.posts | where: 'tags', tag.slug %}
                                {% unless posts.size == 0 %}
                                    <li><a href="{{site.baseurl}}{{tag.url}}">
                                        {{tag.display}}
                                    </a></li>
                                {% endunless %}
                            {% endfor %}
                        </ul>
                    </div>
                {% endunless %}
            {% endunless %}
        </div>
    </div>
</div>

<div id="blog-social" class="blog-social">
    {% include social.md %}
</div>
    
{% include foot.md %}