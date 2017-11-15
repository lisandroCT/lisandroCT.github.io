<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Independent game programmer from Argentina.">
    <title>{{site.title}}</title>
 
    <!--[if lte IE 8]>
        <link rel="stylesheet" href="https://unpkg.com/purecss@1.0.0/build/base-min.css">
        <link rel="stylesheet" href="https://unpkg.com/purecss@1.0.0/build/grids-min.css">
        <link rel="stylesheet" href="https://unpkg.com/purecss@1.0.0/build/grids-responsive-old-ie-min.css">
    <![endif]-->
    <!--[if gt IE 8]><!-->
        <link rel="stylesheet" href="https://unpkg.com/purecss@1.0.0/build/base-min.css">
        <link rel="stylesheet" href="https://unpkg.com/purecss@1.0.0/build/grids-min.css">
        <link rel="stylesheet" href="https://unpkg.com/purecss@1.0.0/build/grids-responsive-min.css">
    <!--<![endif]-->
 
    <link rel="stylesheet" href="https://netdna.bootstrapcdn.com/font-awesome/4.0.3/css/font-awesome.css">
    <link href="https://fonts.googleapis.com/css?family=Dosis:400,700|Roboto:300,700|Patrick+Hand" rel="stylesheet">
 
    <link rel="stylesheet" href="{{site.baseurl}}/css/styles.css">
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