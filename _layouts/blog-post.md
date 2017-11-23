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
    {% assign comments = site.data.comments[page.slug] | where: "parent", "" %}
    {% unless comments.size == 0 %}
        <h1>Comments</h1>
        {% for comment in comments %}
            {% assign id = comment._id %}
            {% assign message = comment.message %}
            {% assign name = comment.name %}
            {% assign email = comment.email %}
            {% assign date = comment.date %}
    
            {% include comment.md id=id message=message name=name email=email date=date %}
        {% endfor %}
        <div style="height: 2em;"></div>
    {% endunless %}
    
    <h1 id="comment">Leave a comment <span id="replying-label" class="hidden" style="float: right">Replying <a href="#comment" onclick="cancelReply()"><i class="fa fa-times" aria-hidden="true"></i></a><span></h1>
    {% include comment-form.md %}
</div>