<div class="blog-content">
    {% unless include.title == null %}
        <h1>{{include.title}}</h1>
    {% endunless %}

    <div class="post-frame">
        <div class="pure-g">
            <div class="pure-u-1 pure-u-sm-2-5">
                <a href="{{post.url}}">
                    <img class="pure-img-responsive" src="{{site.baseurl}}/img/blog/{{include.post.img}}">
                </a>
            </div>
            <div class="post-excerpt pure-u-1 pure-u-sm-3-5">
                {% include post-header.md post=include.post %}

                {{include.post.excerpt}}
            </div>
        </div>
    </div>
</div>