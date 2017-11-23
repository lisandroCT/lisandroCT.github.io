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
    {% assign comments = site.data.comments[page.slug] %}
    {% unless comments == null %}
        {% assign parents = site.data.comments[page.slug] | where: "parent", "" | sort:"date" %}
        {% unless parents.size == 0 %}
            <h1>Comments</h1>
            {% for parent in parents %}
                {% assign id = parent._id %}
                {% assign message = parent.message %}
                {% assign name = parent.name %}
                {% assign email = parent.email %}
                {% assign date = parent.date %}

                {% include comment.md id=id message=message name=name email=email date=date %}
            {% endfor %}
            <div style="height: 2em;"></div>
        {% endunless %}
    {% endunless %}
    
    <h1 id="comment">Leave a comment <span id="replying-label" class="hidden" style="float: right">Replying <a href="#comment" onclick="cancelReply()"><i class="fa fa-times" aria-hidden="true"></i></a><span></h1>
    {% include comment-form.md %}
</div>