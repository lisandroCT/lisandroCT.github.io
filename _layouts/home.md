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
                                <img src="{{site.baseurl}}/assets/portfolio/{% if work.img %}{{work.img}}{% else %}placeholder.svg{% endif %}">

                                <h2>
                                    {{work.title}}
                                </h2>

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
                                <img src="{{site.baseurl}}/assets/projects/{% if project.img %}{{project.img}}{% else %}placeholder.svg{% endif %}">

                                <h2>
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
