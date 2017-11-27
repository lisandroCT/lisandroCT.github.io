---
title: Markup Cheatsheet
layout: blog-article
permalink: /blog/markup/
---
:+1:

Since this is a Jekyll blog, it uses Markdown and Liquid markup languages. This is a basic cheatsheet of my personal preferences, but there are many ways to achieve the same results. For further information, check Markdown and Liquid documentation.

I encourage you to follow these guidelines in comments since it's guaranteed it will render just fine.

## Paragraphs
A paragraph is simply one or more consecutive lines of text, separated by one or more blank lines.

For example:
{% highlight markdown %}
This is a paragraph.

This is another paragraph.
{% endhighlight %}

## Headers
Headers use 2-6 hash characters at the start of the line, corresponding to header levels 2-6 (h1 is reserved).

For example:
{% highlight markdown %}
## Header 2

### Header 3

###### Header 6
{% endhighlight %}

## Blockquotes
Markdown uses email-style > characters for blockquoting. You can hard wrap the text and put a > before every line, or be lazy and only put the > before the first line of a hard-wrapped paragraph.

For example:
{% highlight markdown %}
> This is a blockquote with two paragraphs.
> 
> Paragraph 2.
{% endhighlight %}

## Unordered lists
Unordered lists use asterisks, pluses, and hyphens — interchangably — as list markers.

For example:
{% highlight markdown %}
*   Red
*   Green
*   Blue

+   Red
+   Green
+   Blue

-   Red
-   Green
-   Blue
{% endhighlight %}

## Ordered lists
Ordered lists use numbers followed by periods. You can backslash-escape the period to avoid triggering a list by accident.

For example:
{% highlight markdown %}
1.   First element
2.   Second element
3.   Third element

1\. This is not an ordered list element.
{% endhighlight %}

## Code snippets
To produce a code block, wrap your code between `{% raw  %}{% highlight (optional-language) (linenos) %}{% endraw  %}` and `{% raw  %}{% endhighlight %}{% endraw  %}`. The `linenos` word at the end of the opening highlight tag is optional and it includes line-numbers to the snippet.

For example:
{% highlight markdown %}
{% raw  %}
{% highlight kotlin linenos %}
fun greet() {
    println("Hello, world!")
}
{% endhighlight %}
{% endraw  %}
{% endhighlight %}

To write inline code, wrap your code between backtick quotes (`).

For example:
{% highlight markdown %}
The `greet` method prints 'Hello, world!'.
{% endhighlight %}

## Horizontal rules
Horizontal rule tags (<hr/>) are produced by placing three or more hyphens, asterisks, or underscores on a line by themselves. If you wish, you may use spaces between the hyphens or asterisks.

For example:
{% highlight markdown %}
{% raw  %}
* * *

***

*****

- - -

---------------------------------------
{% endraw  %}
{% endhighlight %}

## Links
A link is composed of a set of square brackets, containing the link text; immediately followed by a set of regular parentheses, containing the URL where the link points at (along with an optional title, surrounded in quotes).

For example:
{% highlight markdown %}
This is [an example](http://example.com/ "Title") inline link.
{% endhighlight %}

### Automatic links
Markdown supports a shortcut style for creating “automatic” links for URLs and email addresses: simply surround the URL or email address with angle brackets.

For example:
{% highlight markdown %}
<http://example.com/>

<address@example.com>
{% endhighlight %}

## Images
The image syntax resembles the syntax for links. Images consist in a an exclamation mark (!); followed by a set of square brackets, containing the alt attribute text for the image; followed by a set of parentheses, containing the URL or path to the image, and an optional title attribute enclosed in double or single quotes.

For example:
{% highlight markdown %}
![Alt text](/path/to/img.jpg "Optional title")
{% endhighlight %}

## Emphasis
Markdown treats asterisks (*) and underscores (_) as indicators of emphasis. Text wrapped with one * or _ will be wrapped with an HTML <em> tag (i.e. italics); double *’s or _’s will be wrapped with an HTML <strong> tag (i.e. bold). Strikethrough uses two tildes (~).

For example:
{% highlight markdown %}
*Italics*

_Italics_

**Bold**

__Bold__

**_Bold and italics_**

__*Bold and italics*__

*__Bold and italics__*

_**Bold and italics**_

***Bold and italics***

___Bold and italics___

~~Strikethrough~~
{% endhighlight %}