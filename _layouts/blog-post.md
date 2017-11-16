---
layout: blog
---
<div class="blog-content">
    <div class="post-frame">
        <img class="cover hidden-md" src="{{site.baseurl}}/img/blog/covers/{{page.img}}">
        
        {% include post-header.md post=page %}
        
        {% highlight kotlin linenos %}{{page.snippet}}{% endhighlight %}
        
        {{content}}
    </div>
</div>