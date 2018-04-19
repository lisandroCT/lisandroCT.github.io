{% include head.md %}

{% include splash.md %}

<div class="content-wrapper">
    <section>
        <div class="portfolio" id="portfolio">
            <h1 class="is-center">Portfolio</h1>

            <div class="pure-g">
                {% unless site.categories.portfolio == null %}
                    {% assign sorted_portfolio = site.categories.portfolio | sort:"order" %}
                    {% for work in sorted_portfolio %}
                        <div class="l-box pure-u-1 pure-u-sm-1-2 pure-u-md-1-3 pure-u-lg-1-4">
                            <div class="frame">
                                <div {% if work.webm or work.mp4 %}onmouseover="showVideo(this)" onmouseout="showImg(this)"{% endif %}>
                                    {% capture base %}{{site.baseurl}}/assets/portfolio{% endcapture %}
                                    {% capture img %}{{base}}/{% if work.img %}{{work.img}}{% else %}placeholder.svg{% endif %}{% endcapture %}
                                    {% capture video-poster %}{% if work.video-poster %}{{base}}/{{work.video-poster}}{% else %}{{img}}{% endif %}{% endcapture %}
                                    <img src="{{img}}">
                                    {% if work.webm or work.mp4 %}
                                        <video loop muted controls preload="auto" width="100%" style="background-image: url('{{video-poster}}')" poster="{{base}}/video-poster.svg">
                                            {% if work.webm %}
                                                <source src="{{base}}/{{work.webm}}" type="video/webm">
                                            {% endif %}
                                            {% if work.mp4 %}
                                                <source src="{{base}}/{{work.mp4}}" type="video/mp4">
                                            {% endif %}
                                            <img src="{{base}}/video-not-supported.svg">
                                        </video>
                                    {% endif %}
                                </div>

                                <h2 class="title">
                                    {{work.title}}
                                </h2>
                                
                                {% if work.website or work.youtube or work.play-store or work.app-store %}
                                    <div class="resources">
                                        {% if work.play-store %}
                                            <a href="https://play.google.com/store/apps/details?id={{work.play-store}}"><i class="fab fa-google-play"></i></a>
                                        {% endif %}
                                        {% if work.app-store %}
                                            <a href="https://itunes.apple.com/app/id{{work.app-store}}"><i class="fab fa-app-store"></i></a>
                                        {% endif %}
                                        {% if work.youtube %}
                                            <a href="https://www.youtube.com/watch?v={{work.youtube}}"><i class="fab fa-youtube"></i></a>
                                        {% endif %}
                                        {% if work.website %}
                                            <a href="{{work.website}}"><i class="fas fa-globe"></i></a>
                                        {% endif %}
                                    </div>
                                {% endif %}
                                
                                {{work.content}}
                            </div>
                        </div>
                    {% endfor %}
                {% endunless %}
            </div>
        </div>
    </section>
    
    <section>
        <div class="projects" id="projects">
            <h1 class="is-center">Projects</h1>

            <div class="pure-g">
                {% unless site.categories.projects == null %}
                    {% assign sorted_projects = site.categories.projects | sort:"order" %}
                    {% for project in sorted_projects %}
                        <div class="l-box pure-u-1 pure-u-lg-1-2">
                            <div class="frame">
                                <div>
                                    <img src="{{site.baseurl}}/assets/projects/{% if project.img %}{{project.img}}{% else %}placeholder.svg{% endif %}">
                                </div>

                                <h2 class="title">
                                    {{project.title}}
                                </h2>

                                {{project.content}}
                            </div>
                        </div>
                    {% endfor %}
                {% endunless %}
            </div>
        </div>
    </section>
</div>

{% include foot.md %}
