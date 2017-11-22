<form id="comment-form" method="POST" action="{{site.staticman_url}}" class="pure-form pure-form-stacked comment-form">
    <input name="options[reCaptcha][siteKey]" value="6Le1GDkUAAAAAIL1mWQaHx3uapvh_ek2Gjpz4Fpn" type="hidden" >
    <input name="options[reCaptcha][secret]" value="QYZHb1y4/fYu7zbUO8HIK2HJplQAqBgYdao/BXJfbF4Ywwm8OpCmQhR56sGtMjan4kytj84AOF87kNpwu1Mb7Oppgj3xIX9q0k08bQxEOPGV5Z0MXRcteT1EUm4WYOb2j80r1pOkG7qZ32y3tEakCQqvT7pHjus18kOT4MhzhKI=" type="hidden">
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
        <div class="g-recaptcha" data-sitekey="6Le1GDkUAAAAAIL1mWQaHx3uapvh_ek2Gjpz4Fpn"></div>
    </fieldset>

    <div id="comment-log" class="log hidden">

    </div>

    <fieldset>
        <button id="comment-form-submit" type="submit" class="pure-button pure-button-primary">Send comment</button>
    </fieldset>
</form>