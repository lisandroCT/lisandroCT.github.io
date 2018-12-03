---
title: Emojis Cheatsheet
layout: blog-article
permalink: /blog/emojis-cheatsheet/
---
You can use emojis within comments, just like you would in a comment or issue within a repository on GitHub.

<div class="pure-g">
    {% for emoji in site.data.emojis %}
        {% capture s %}:{{emoji[0]}}:  `:{{emoji[0]}}:`{% endcapture %}
        <div class="pure-u-1 pure-u-lg-1-2 pure-u-xl-1-3">
            {{s | markdownify}}
        </div>
    {% endfor %}
</div>