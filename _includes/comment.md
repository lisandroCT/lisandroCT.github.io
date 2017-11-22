<div class="comment">
    <img class="avatar" src="https://www.gravatar.com/avatar/{{include.email}}"/>
    <div class="comment-content">
        <h1>{{include.name}}</h1>
        <p class="details">
            <span class="date"><i class="fa fa-calendar" aria-hidden="true"></i> {{include.date | date_to_long_string }}</span>
        </p>
        {{include.message}}
    </div>
</div>