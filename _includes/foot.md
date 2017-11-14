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
        var navLinks = document.querySelectorAll('nav div a[href^="#"]');
        
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
    var navbar = document.getElementById("navbar");
    var shadow = document.getElementById("shadow");
 
    function openNav() {
        navbar.style.left = "0";
        shadow.style.display = "inline";
        shadow.style.visibility = "visible";
    }
 
    function closeNav() {
        navbar.style.left = "-10em";
        shadow.style.display = "none";
        shadow.style.visibility = "hidden";
    }
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
</body>
</html>