<form id="comment-form" method="POST" action="{{site.staticman_url}}" class="pure-form pure-form-stacked comment-form">
    <input name="options[reCaptcha][siteKey]" value="6Le1GDkUAAAAAIL1mWQaHx3uapvh_ek2Gjpz4Fpn" type="hidden">
    <input name="options[reCaptcha][secret]" value="QYZHb1y4/fYu7zbUO8HIK2HJplQAqBgYdao/BXJfbF4Ywwm8OpCmQhR56sGtMjan4kytj84AOF87kNpwu1Mb7Oppgj3xIX9q0k08bQxEOPGV5Z0MXRcteT1EUm4WYOb2j80r1pOkG7qZ32y3tEakCQqvT7pHjus18kOT4MhzhKI=" type="hidden">
    <input name="options[slug]" type="hidden" value="{{page.slug}}">
    
    <input id="comment-form-parent" name="fields[parent]" value="" type="hidden">
    <input id="comment-form-quoted" name="fields[quoted]" value="" type="hidden">

    <fieldset>            
        <label for="comment-form-message">Message <small>(<a href="{{site.baseurl}}/blog/markdown-cheatsheet">Markdown</a> and <a href="{{site.baseurl}}/blog/emojis-cheatsheet">emojis</a> are allowed)</small></label>
        <textarea id="comment-form-message" name="fields[message]" class="pure-input-1 message-textarea" required></textarea>

        <div class="pure-g">
            <div class="pure-u-1 pure-u-lg-8-24 name-input">
                <label for="comment-form-name">Name or nickname</label>
                <input id="comment-form-name" name="fields[name]" type="text" class="pure-input-1" required>
            </div>

            <div class="pure-u-1 pure-u-lg-8-24 email-input">
                <label for="comment-form-email">Email* <small>(optional, it's not stored)</small></label>
                <input id="comment-form-email" name="fields[email]" type="email" class="pure-input-1">
            </div>

            <div class="pure-u-1 pure-u-lg-8-24 website-input">
                <label for="comment-form-website">Website <small>(optional)</small></label>
                <input id="comment-form-website" name="fields[website]" type="url" class="pure-input-1">
            </div>
        </div>
    </fieldset>

    <fieldset class="hidden">
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
    
    <fieldset>
        <p>* A hash is used for <a href="http://gravatar.com">Gravatar</a> image. The address is not stored in any way.</p>
    </fieldset>
</form>