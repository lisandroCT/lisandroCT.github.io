---
layout: blog
---
<div class="blog-content">
    <div class="post-frame">
        <img class="pure-img-responsive" src="{{site.baseurl}}/img/blog/{{page.img}}">
        
        {% include post-header.md post=page %}
        
        {{content}}
    </div>
</div>