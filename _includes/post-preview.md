<div class="blog-content" style="border-color: rgb({% include post-color.md post=post %})">
    {% unless include.title == null %}
        <h1>{{include.title}}</h1>
    {% endunless %}

    <div class="post-frame">
        {% include post-header.md post=include.post %}

        {{include.post.excerpt}}

        <p style="margin-top: 1em">
            <a href="{{post.url}}">Read more...</a>
        </p>
    </div>
</div>