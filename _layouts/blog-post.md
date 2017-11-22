---
layout: blog
---
<div class="blog-content">
    <div class="post-frame">
        <a href="{{post.url}}">
            <div class="cover snippet">
                {% highlight kotlin %}{{page.snippet}}{% endhighlight %}
            </div>
        </a>
        
        {% include post-header.md post=page %}
        
        <div class="user-content">
            {{content}}
        </div>
    </div>
</div>

<div class="blog-content">
    {% assign comments = site.data.comments[page.slug] | sort %}
    {% unless comments.size == 0 %}
        <h1>Comments</h1>
        {% for comment in comments %}
            {% assign message = comment[1].message %}
            {% assign name = comment[1].name %}
            {% assign email = comment[1].email %}
            {% assign date = comment[1].date %}
    
            {% include comment.md message=message name=name email=email date=date %}
        {% endfor %}
        <div style="height: 2em;"></div>
    {% endunless %}
    
    <h1>Leave a comment</h1>
    {% include comment-form.md %}
</div>