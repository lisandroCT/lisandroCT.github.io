<div class="blog-content">
    {% unless include.title == null %}
        <h1>{{include.title}}</h1>
    {% endunless %}

    <div class="post-frame">
        <div class="pure-g">
            <div class="pure-u-1 pure-u-sm-1-3">
                <a href="{{post.url}}">
                    <img class="thumbnail" src="{{site.baseurl}}/img/blog/thumbnails/{{include.post.img}}">
                </a>
            </div>
            <div class="post-excerpt pure-u-1 pure-u-sm-2-3">
                {% include post-header.md post=include.post %}

                {{include.post.excerpt}}
                
                <p style="margin-top: 1em">
                    <a href="{{post.url}}">Read more...</a>
                </p>
            </div>
        </div>
    </div>
</div>