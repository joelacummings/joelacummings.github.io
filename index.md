---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
---

<div class="content">
	<div class="posts">
		{% for post in site.posts limit:50 %}
			<a href="{% if post.external_url %}{{ post.external_url }}{% else %}{{ post.url }}{% endif %}">
				<div class="c">
					{% if post.photo_url %}
						<h3>{{ post.title }}</h3>
						<div class="image" style="background-image:url(' {{ post.photo_url }}')"></div>
					{% else %}
						<h3 class="text">{{ post.title }}</h3>
						<div class="body">
							<p>{% if post.description %}
									{{ post.description | markdownify | strip_html }}
								{% else %}
									{{ post.excerpt | strip_html }}
								{% endif %}
								<info datetime="{{ page.date | date: "%Y-%m-%d" }}">
									{{ post.date | date: "%b %Y" }}
								</info>
							</p>
						</div>
					{% endif %}
				</div>
			</a>
		{% endfor %}
		<div class="breaker"></div>
		<div class="end">
		</div>
	</div>
</div>
