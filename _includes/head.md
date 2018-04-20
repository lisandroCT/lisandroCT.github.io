<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% if page.title %}{{page.title}} | {% endif %}{{site.title}}</title>
    <meta name="description" content="{% if page.description %}{{ page.description }}{% else %}{% if page.excerpt %}{{ page.excerpt | strip_html | strip | strip_newlines }}{% else %}{{site.description}}{% endif %}{% endif %}">
    <meta name="keywords" content="{% unless site.blog-tags == null %}{% unless site.blog-tags.size == 0 %}{% for tag in site.blog-tags %}{% if page.tags contains tag.slug %}{{tag.display | downcase}}, {% endif %}{% endfor %}{% endunless %}{% endunless %}{% if page.url contains "blog" %}blog, {% endif %}{% for keyword in site.keywords %}{{keyword | downcase}}{% unless forloop.last %}, {% endunless} %}{% endfor %}">
    <meta name="author" content="Lisandro Crespo">
    
    <link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png">
    <link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png">
    <link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png">
    <link rel="manifest" href="/manifest.json">
    <meta name="theme-color" content="#ffffff">
    
    <style>
        *{-webkit-box-sizing:border-box;-moz-box-sizing:border-box;box-sizing:border-box}body{line-height:normal;color:#292c37;font-size:13px;background:#292c37}html{font-family:'Roboto',sans-serif;font-weight:300}html a{color:#813136;text-decoration:none}img,video{border-radius:.2em}.header{padding:.5em;text-align:center;background:#292c37;color:#ccc;position:fixed;top:0;width:100%;border-bottom:none;z-index:5}.header .logo{text-transform:none;color:#ccc;font-size:190%;font-family:'Dosis',sans-serif;font-weight:400}.header .logo span{color:#813136;font-weight:700}.header .bars,.header .navigation{position:absolute;transform:translateY(-50%);top:50%}.header .bars{left:1em;font-size:135%}.header .navigation{right:2em;display:none;visibility:hidden;font-weight:700}.header .navigation a{color:#ccc;margin-right:1em}.shadow,.side-navigation{position:fixed;height:100%}.side-navigation{top:0;left:-10em;padding-top:2.5em;background:#292c37;font-weight:700;font-size:120%;overflow-x:hidden;z-index:15;width:10em}.side-navigation a{display:block;color:#ccc;width:100%;margin-left:1em;margin-bottom:1em}.shadow{z-index:10;width:100%;background-color:rgba(0,0,0,.3);display:none;visibility:hidden}.splash-container{background:#292c37;z-index:1;overflow:hidden;width:100%;height:100%;top:0;left:0;position:fixed!important;color:#ccc}.social,.splash{position:absolute;left:0;right:0;margin-left:auto;margin-right:auto;text-align:center}.splash{top:4em;padding-bottom:3em;overflow:auto;bottom:4em;width:90%}.splash a{font-weight:700}.social{bottom:1em;width:80%;letter-spacing:.5em;font-size:150%}.social a{color:#ccc}.profile-picture{border-radius:50%;height:10em;width:auto;display:none;visibility:hidden}.presentation{font-size:150%}.frame img{width:100%;height:auto}.frame video{display:none;background-size:cover}@media (min-width:35.5em){.profile-picture{display:inline;visibility:visible}.social{font-size:180%}}@media (min-width:48em){body{font-size:16px}.header{padding-left:2em;text-align:left}.splash{width:80%;max-width:70em}.header .logo{width:100%}.header .bars,.side-navigation{display:none;visibility:hidden}.header .navigation{display:inline;visibility:visible}}
    </style>
    
    {% if page.layout == "blog-post" %}
        <script src='https://www.google.com/recaptcha/api.js' async defer></script>
    {% endif %}
</head>
    
<body>
    
<div class="header" id="header">
    <i class="fa fa-bars bars" aria-hidden="true" onclick="openNav()"></i>
    <nav>
        <a class="logo" href="{{site.baseurl}}/#"><span>L</span>isandro <span>C</span>respo</a>
 
        <div class="navigation">
            {% include navigation.md %}
        </div>
    </nav>
</div>
 
<nav>
    <div class="nav side-navigation" id="navbar">
        {% include navigation.md %}
    </div>
</nav>
    
<div class="shadow" id="shadow" onclick="closeNav()"></div>