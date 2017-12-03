<div class="comment">
    <img class="avatar" src="https://www.gravatar.com/avatar/{{include.email}}"/>
    <a href="#comment" onclick="reply('{{include.id}}')"><span class="reply"><i class="fa fa-reply" aria-hidden="true"></i></span></a>
    <div class="comment-content">
        <div class="user-content">{{include.message | markdownify}}</div>
    </div>
    <p class="details">
        <span class="time"><i class="fa fa-clock-o" aria-hidden="true"></i> {{include.date | date: "%I:%M %p" }}</span>
        <span class="date"><i class="fa fa-calendar" aria-hidden="true"></i> {{include.date | date_to_long_string }}</span>
        {% unless include.website == null or include.website == "" %}<a href="{{include.website}}">{% endunless %}<span class="author"><i class="fa fa-pencil" aria-hidden="true"></i> {{include.name}}</span>{% unless include.website == null or include.website == "" %}</a>{% endunless %}
    </p>
    
    {% assign comments = site.data.comments[page.slug] | where: "parent", {{include.id}} | sort:"date" %}
    {% for comment in comments %}
        <div class="comment">
            <img class="avatar" src="https://www.gravatar.com/avatar/{{comment.email}}"/>
            <a href="#comment" onclick="reply('{{include.id}}', '{{comment.id}}')"><span class="reply"><i class="fa fa-reply" aria-hidden="true"></i></span></a>
            {% if comment.quoted %}
            <div class="comment-quote">
                {% assign quoted = site.data.comments[page.slug] | where: "id", {{comment.quoted}} %}
                {% unless quoted == null %}
                    <div class="user-content">{{quoted.message | markdownify}}</div>
                {% endunless %}
            </div>
            {% endif %}
            <div class="comment-content">
                <div class="user-content">{{comment.message | markdownify}}</div>
            </div>
            <p class="details">
                <span class="time"><i class="fa fa-clock-o" aria-hidden="true"></i> {{comment.date | date: "%I:%M %p" }}</span>
                <span class="date"><i class="fa fa-calendar" aria-hidden="true"></i> {{comment.date | date_to_long_string }}</span>
                {% unless comment.website == null or comment.website == "" %}<a href="{{comment.website}}">{% endunless %}<span class="author"><i class="fa fa-pencil" aria-hidden="true"></i> {{comment.name}}</span>{% unless comment.website == null or comment.website == "" %}</a>{% endunless %}
            </p>
        </div>
    {% endfor %}
</div>