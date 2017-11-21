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
    <form id="comment-form" method="post" action="https://api.staticman.net/v1/entry/{{site.repository}}/{{site.staticman.branch}}" class="pure-form pure-form-stacked">
        <fieldset>
            <input name="options[slug]" type="hidden" value="{{ page.slug }}">
            
            <label for="comment-form-message">Message <small>(<a href="https://kramdown.gettalong.org/quickref.html">Markdown</a> is allowed)</small></label>
            <textarea id="comment-form-message" name="fields[message]" class="pure-input-1" required></textarea>
            
            <div class="pure-g">
                <div class="pure-u-1 pure-u-lg-9-24">
                    <label for="comment-form-name">Name or nickname</label>
                    <input id="comment-form-name" name="fields[name]" type="text" class="pure-input-1" required>
                </div>
                
                <div class="pure-u-lg-1-24 hidden-md"></div>

                <div class="pure-u-1 pure-u-lg-14-24">
                    <label for="comment-form-email">Email <small>(used for <a href="http://gravatar.com">Gravatar</a> image and reply notifications)</small></label>
                    <input id="comment-form-email" name="fields[email]" type="email" class="pure-input-1" required>
                </div>
            </div>
        </fieldset>
        
        <fieldset>
            <div class="g-recaptcha" data-sitekey="6Le1GDkUAAAAAIL1mWQaHx3uapvh_ek2Gjpz4Fpn"></div>
        </fieldset>

        <fieldset>
            <label for="terms" class="pure-checkbox">
                <input id="comment-form-subscribe" type="checkbox"> Notify me of replies by email.
            </label>
        </fieldset>
        
        <fieldset>
            <button id="comment-form-submit" type="submit" class="pure-button pure-button-primary">Send comment</button>
        </fieldset>
    </form>
</div>

<script type="text/javascript">
    (function() {
        var form = document.getElementById("comment-form");
        var button = document.getElementById("comment-form-submit");
        
        form.onsubmit = function(event) {
            event.preventDefault();
            
            sendData();
        };
        
        function sendData() {
            button.disabled = true;
            
            var xhr = new XMLHttpRequest();
            var fd = new FormData(form);
            
            
            xhr.onload = function(event) {
                if(xhr.status == 200) {
                    onLoad();
                } else {
                    onError();
                }
                
                button.disabled = false;
            };
            
            xhr.onerror = function(event) {
                onError();
                
                button.disabled = false;
            };
            
            xhr.open(form.method, form.action);
            xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
            xhr.send(fd);
        }
        
        function onLoad() {
            alert("Success!");
        }
        
        function onError() {
            alert("Snap!");
        }
    })();
</script>