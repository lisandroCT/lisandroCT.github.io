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
        
        {{content}}
    </div>
</div>

<div class="blog-content">
    <h1>Leave a comment</h1>
    <form id="comment-form" method="POST" action="{{site.staticman_url}}" class="pure-form pure-form-stacked comment-form">
        <input name="options[slug]" type="hidden" value="{{page.slug}}">
        
        <fieldset>            
            <label for="comment-form-message">Message <small>(<a href="https://kramdown.gettalong.org/quickref.html">Markdown</a> is allowed)</small></label>
            <textarea id="comment-form-message" name="fields[message]" class="pure-input-1 message-textarea" required></textarea>
            
            <div class="pure-g">
                <div class="pure-u-1 pure-u-lg-9-24 name-input">
                    <label for="comment-form-name">Name or nickname</label>
                    <input id="comment-form-name" name="fields[name]" type="text" class="pure-input-1" required>
                </div>
                
                <div class="pure-u-1 pure-u-lg-15-24 email-input">
                    <label for="comment-form-email">Email <small>(used for <a href="http://gravatar.com">Gravatar</a> image and reply notifications, will not be public)</small></label>
                    <input id="comment-form-email" name="fields[email]" type="email" class="pure-input-1" required>
                </div>
            </div>
        </fieldset>
        
        <fieldset>
            <label for="terms" class="pure-checkbox">
                <input id="comment-form-subscribe" name="field[subscribe]" type="checkbox"> Notify me of replies by email.
            </label>
        </fieldset>
        
        <fieldset>
            <button id="comment-form-submit" type="submit" class="pure-button pure-button-primary">Send comment</button>
        </fieldset>
    </form>
</div>