---
#
# By default, this is an index or homepage with texts
# changed it writings layout
# To change the home page layout, edit the _layouts/home.html file.
# https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#
layout: default
---

I love to tinkering stuff on my computer. that it has taught me a lot of what I know. 
Technology has often found ways to pull me into new hobbies.


<div class="items-list">
{% for post in site.posts limit:10  %}
{% assign currentdate = post.date | date: "%Y" %}
{% if currentdate != date %}
    {% unless forloop.first %}</ul>{% endunless %}
    <h2 id="year-{{post.date | date: "%Y"}}">{{ currentdate }}</h2>
    <ul>
      {% assign date = currentdate %}
    {% endif %}
      <li class="items-list">
        <time datetime="{{ post.date | date: '%Y-%m-%d' }}">{{ post.date | date: '%b %d' }}</time>
        <a href="{{ site.baseurl | prepend: site.url }}{{ post.url }}">{{ post.title }}</a>
      </li>
  {% endfor %}
</ul>
</div>


<br>
**[All writings](/writings)**