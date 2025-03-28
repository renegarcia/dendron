
# Highlight current page in navbar



You can get the name of the url (referenced in your urlpatterns). Then set the 'active' class if the url matches.

```python
{% with url_name=request.resolver_match.url_name %}
<li class="dropdown {% if url_name == 'index' %}active{% endif %}"
   <a href="{% url 'index' %}" >Home </a>
</li>
<li>...</li>
{% endwith %}
```

In practice it is also useful to prepend the app_name into the path, por example, there
might be the `about:index` page and the `home:index` page, which both have the same
`url_name` as of `Django 4.2`. In order to deal with this case, we also get the app name
from the resolver,

```python
{% with app_name=request.resolver_match.app_names.0 url_name=request.resolver_match.url_name %}
<li class="dropdown {% if app_name == 'home' and url_name == 'index' %}active{% endif %}"
   <a href="{% url 'home:index' %}" >Home </a>
</li>
<li>...</li>
{% endwith %}
```


# References

1. [Django: Highlight current page in navbar](https://stackoverflow.com/questions/39639264/django-highlight-current-page-in-navbar)
2. [get app name from url in django](https://stackoverflow.com/questions/19261269/get-app-name-from-url-in-django)