<h3>Blog Posts</h3>
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

{% for category in page.categories %}
  <h3>{{ category }}</h3>
  <ul>
    {% for page in site.categories[category] %}
      <li><a href="{{ page.url }}">{{ page.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
