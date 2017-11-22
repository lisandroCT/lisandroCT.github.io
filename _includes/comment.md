<div class="comment">
    <img class="avatar" src="https://www.gravatar.com/avatar/{{include.email}}"/>
    <div class="comment-content">
        <div class="user-content">{{include.message | markdownify}}</div>
    </div>
    <p class="details">
        <span class="time"><i class="fa fa-clock-o" aria-hidden="true"></i> {{include.date | date: "%I:%M %p" }}</span>
        <span class="date"><i class="fa fa-calendar" aria-hidden="true"></i> {{include.date | date_to_long_string }}</span>
        <span class="author"><i class="fa fa-pencil" aria-hidden="true"></i> {{include.name}}</span>
        <span class="reply" style="float: right"><i class="fa fa-reply" aria-hidden="true"></i></span>
    </p>
</div>