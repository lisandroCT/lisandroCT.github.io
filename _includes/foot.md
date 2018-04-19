<script type="text/javascript" src="{{site.baseurl}}/js/smooth-scroll.min.js"></script>
<script type="text/javascript">
    (function() {
        var header = document.getElementById("header");
        var headerHeight = getHeaderHeight() + 5;

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
{% if page.layout == "home" %}
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
    <script>
        function showVideo(div) {
            var video = div.getElementsByTagName('video')[0];
            if(video == null) {
                return;
            }
            
            var img = div.getElementsByTagName('img')[0];
            
            video.play();
            
            img.style.display = "none";
            video.style.display = "inline";
        }
        function showImg(div) {
            var video = div.getElementsByTagName('video')[0];
            if(video == null) {
                return;
            }
            
            var img = div.getElementsByTagName('img')[0];
            
            video.pause();
            
            img.style.display = "inline";
            video.style.display = "none";
        }
    </script>
{% endif %}
{% if page.layout == "blog-post" %}
    <script type="text/javascript">
        function serialize(form) {
            if (!form || form.nodeName !== "FORM") {
                return
            }
            var i, j, q = [];
            for (i = form.elements.length - 1; i >= 0; i = i - 1) {
                if (form.elements[i].name === "") {
                    continue
                }
                switch (form.elements[i].nodeName) {
                    case "INPUT":
                        switch (form.elements[i].type) {
                            case "checkbox":
                            case "radio":
                                if (form.elements[i].checked) {
                                    q.push(form.elements[i].name + "=" + encodeURIComponent(form.elements[i].value))
                                }
                                break;
                            case "file":
                                break;
                            default:
                                q.push(form.elements[i].name + "=" + encodeURIComponent(form.elements[i].value));
                                break;
                        }
                        break;
                    case "TEXTAREA":
                        q.push(form.elements[i].name + "=" + encodeURIComponent(form.elements[i].value));
                        break;
                    case "SELECT":
                        switch (form.elements[i].type) {
                            case "select-one":
                                q.push(form.elements[i].name + "=" + encodeURIComponent(form.elements[i].value));
                                break;
                            case "select-multiple":
                                for (j = form.elements[i].options.length - 1; j >= 0; j = j - 1) {
                                    if (form.elements[i].options[j].selected) {
                                        q.push(form.elements[i].name + "=" + encodeURIComponent(form.elements[i].options[j].value))
                                    }
                                }
                                break
                        }
                        break;
                    case "BUTTON":
                        switch (form.elements[i].type) {
                            case "reset":
                            case "submit":
                            case "button":
                                q.push(form.elements[i].name + "=" + encodeURIComponent(form.elements[i].value));
                                break
                        }
                        break
                }
            }
            return q.join("&")
        };
    </script>
    <script type="text/javascript">
        function reply(parentId) {
            cancelReply();
            
            var parent = document.getElementById("comment-form-parent");
            parent.value = parentId;
            
            var label = document.getElementById("replying-label");
            label.classList.remove("hidden");
        }
        
        function reply(parentId, quotedId) {
            cancelReply();
            
            var parent = document.getElementById("comment-form-parent");
            parent.value = parentId;
            var quote = document.getElementById("comment-form-quote");
            quote.value = quotedId;
            
            var label = document.getElementById("replying-label");
            label.classList.remove("hidden");
        }
    
        function cancelReply() {
            var parent = document.getElementById("comment-form-parent");
            parent.value = "";
            var quote = document.getElementById("comment-form-quote");
            quote.value = "";
            
            var label = document.getElementById("replying-label");
            label.classList.add("hidden");
        }
        
        (function() {
            var form = document.getElementById("comment-form");
            var button = document.getElementById("comment-form-submit");
            var buttonContent = button.innerHTML;
            var log = document.getElementById("comment-log");
            
            var timeout = null;

            form.onsubmit = function(event) {
                event.preventDefault();

                sendData();
            };

            function sendData() {
                disableButton();

                var xhr = new XMLHttpRequest();
                var fd = new FormData(form);

                xhr.onload = function(event) {
                    if(xhr.status == 200) {
                        onSuccess();
                    } else {
                        onError();
                    }

                    enableButton();
                };

                xhr.onerror = function(event) {
                    onError();

                    enableButton();
                };

                xhr.open(form.method, form.action);
                xhr.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
                xhr.send(serialize(form));
            }

            function onSuccess() {
                cancelReply();
            
                grecaptcha.reset();
                form.reset();
                
                log.classList.remove("hidden");
                log.classList.remove("error");
                log.classList.add("success");
                
                clearTimeout(timeout);
                timeout = setTimeout(function() { log.classList.add("hidden"); }, 7000);
                
                log.innerHTML = "<i class='fa fa-check-circle' aria-hidden='true'></i> <strong>Thanks for your comment!</strong> It will show on the site in a few seconds."
            }

            function onError() {
                grecaptcha.reset();
                            
                log.classList.remove("hidden");
                log.classList.remove("success");
                log.classList.add("error");
                
                clearTimeout(timeout);
                timeout = setTimeout(function() { log.classList.add("hidden"); }, 7000);
                
                log.innerHTML = "<i class='fa fa-exclamation-circle' aria-hidden='true'></i> <strong>Sorry, there was an error with your submission.</strong> Please make sure all required fields have been completed and try again."
            }
            
            function enableButton() {
                button.innerHTML = buttonContent;
                button.disabled = false;
            }
            
            function disableButton() {
                button.innerHTML = "<div class='loader'></div>";
                button.disabled = true;
            }
        })();
    </script>
{% endif %}
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
</body>
</html>