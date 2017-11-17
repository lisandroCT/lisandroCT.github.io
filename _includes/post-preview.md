<div class="blog-content">
    {% unless include.title == null %}
        <h1>{{include.title}}</h1>
    {% endunless %}

    <div class="post-frame">
        <div class="pure-g">
            <div class="pure-u-1 pure-u-lg-1-3">
                <a href="{{post.url}}">
                    <div class="thumbnail snippet">
                        {% highlight kotlin %}{{post.snippet}}{% endhighlight %}
                    </div>
                </a>
            </div>
            <div class="post-excerpt pure-u-1 pure-u-lg-2-3">
                {% include post-header.md post=include.post %}

                {{include.post.excerpt}}
                
                <p style="margin-top: 1em">
                    <a href="{{post.url}}">Read more...</a>
                </p>
            </div>
        </div>
    </div>
</div>