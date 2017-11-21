{% include head.md %}

{% include splash.md %}

<div class="content-wrapper">
    <section>
        <div class="portfolio" id="portfolio">
            <h1 class="is-center">Portfolio</h1>

            <div class="pure-g">
                
                {% assign sorted_portfolio = site.categories.portfolio | sort:"order" %}
                {% for work in sorted_portfolio %}
                    <div class="l-box pure-u-1 pure-u-sm-1-2 pure-u-md-1-3 pure-u-lg-1-4">
                        <div class="frame">
                            <img class="pure-img-responsive" src="{{site.baseurl}}/img/{% if work.img %}portfolio/{{work.img}}{% else %}placeholder.svg{% endif %}">
                            
                            <h2>
                                {{work.title}}
                            </h2>
                            
                            {{work.content}}
                        </div>
                    </div>
                {% endfor %}
                
            </div>
        </div>
    </section>
    
    <section>
        <div class="projects" id="projects">
            <h1 class="is-center">Projects</h1>

            <div class="pure-g">
            
                {% assign sorted_projects = site.categories.projects | sort:"order" %}
                {% for project in sorted_projects %}
                    <div class="l-box pure-u-1 pure-u-lg-1-2">
                        <div class="frame">
                            <img class="pure-img-responsive" src="{{site.baseurl}}/img/{% if project.img %}projects/{{project.img}}{% else %}placeholder.svg{% endif %}">
                            
                            <h2>
                                {{project.title}}
                            </h2>
                            
                            {{project.content}}
                        </div>
                    </div>
                {% endfor %}
                
            </div>
        </div>
    </section>
</div>

<script type="text/javascript" src="{{site.baseurl}}/js/smooth-scroll.min.js"></script>
<script type="text/javascript">
    (function() {
        var header = document.getElementById("header");
        var headerHeight = getHeaderHeight();
 
        function getHeaderHeight() {
            //return header.getBoundingClientRect().height;
            var position = header.getBoundingClientRect();
            return position.height;
        }
 
        var scroll = new SmoothScroll('a[href*="#"]', {
            // Speed & Easing
            speed: 500, // Integer. How fast to complete the scroll in milliseconds
            offset: headerHeight // Integer or Function returning an integer. How far to offset the scrolling anchor location in pixels
        });
 
        window.onresize = function(event) {
            headerHeight = getHeaderHeight();
        };
    })();
</script>
<script type="text/javascript">
    (function() {
        'use strict';
 
        var windowHeight = calculateHeight();
        
        var sections = document.querySelectorAll('section [id]');
        var navLinks = document.querySelectorAll('nav div a[href^="{{site.baseurl}}/#"]');
        
        function getClosestSection() {
            var index = -1;
            var max = 0;
            for(var i = 0, n = sections.length; i < n; i++) {
                var percentage = getPercentage(sections[i]);
                
                if(percentage <= 0) {
                    continue;
                }
                
                if(index == -1 || percentage > max) {
                    index = i;
                    max = percentage;
                }
            }
            
            for(var i = 0, n = navLinks.length; i < n; i++) {
                navLinks[i].classList.remove('is-selected');
            }
 
            if(index == -1) {
                return;
            }
            
            selectLink(sections[index].id);
        }
        
        function getPercentage(element) {
            var position = element.getBoundingClientRect();
            
            var top = Math.max(0, position.top);
            var bottom = Math.min(windowHeight, position.bottom);
            if(position.top > windowHeight || position.bottom < 0) {
                return 0;
            }
            
            return (bottom - top) / windowHeight;
        }
        
        function selectLink(id) {
            for(var i = 0, n = navLinks.length; i < n; i++) {
                var element = navLinks[i];
                
                if(element.href.split("#")[1] == id) {
                    element.classList.add('is-selected');
                }
            }
        }
        
        function calculateHeight() {
            var w = window,
                d = document,
                e = d.documentElement,
                g = d.getElementsByTagName('body')[0],
                y = w.innerHeight|| e.clientHeight|| g.clientHeight;
            
            return y;
        }
        
        window.onresize = function(event) {
            windowHeight = calculateHeight();
            getClosestSection();
        };
        
        window.onscroll = function(event) {
            getClosestSection();
        };
    })();
</script>
<script type="text/javascript">
(function() {
    var frames = document.getElementsByClassName("frame");
    
    for(var i = 0, n = frames.length; i < n; i++) {
        var degrees = Math.random() * 3 - 1.5;
        
        frames[i].setAttribute("style", "-ms-transform: rotate(" + degrees + "deg);");
        frames[i].setAttribute("style", "-webkit-transform: rotate(" + degrees + "deg);");
        frames[i].setAttribute("style", "transform: rotate(" + degrees + "deg);");
    }
})();
</script>

{% include foot.md %}
