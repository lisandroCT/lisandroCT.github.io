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
    
    <link rel="stylesheet" href="{{site.baseurl}}/css/styles.css">
    
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