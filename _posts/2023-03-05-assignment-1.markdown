---
layout: post
title: "Assignment 1"
date: 2023-03-05 3:42:07 -0500
categories: assignments
permalink: /assignments/1/
---

<style type="text/css">
  .card {
    /* Add shadows to create the "card" effect */
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    transition: 0.3s;
  }

  /* On mouse-over, add a deeper shadow */
  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(0, 0, 0, 0.2);
  }

  /* Add some padding inside the card container */
  .container {
    border-top: solid 1px grey;
    padding: 2px 16px;
  }

  .row {
    display: flex;
  }

  .column {
    flex: 20%;
    padding: 5px;
  }

  /* Responsive layout - makes the columns stack on top of each other instead of next to each other */
  @media screen and (max-width: 500px) {
    .column {
      width: 100%;
    }
  }
</style>

<div class="row">
{% assign image_names = "JS Paint (pencil only),JS Paint (all tools),GIMP,InkScape" | split: ',' %}

{% for image in site.static_files %}
  {% if image.path contains 'a1' %}
    <div class="card column" style="width:300px">
      <a href="{{ site.baseurl }}/assignments/1/p{{ forloop.index }}/">
        <img src="{{ site.baseurl }}/{{ image.path }}" alt="{{ image.name }}" width="100%">
      </a>
      <div class="container">
        <h4><b>Portrait {{ forloop.index }}</b></h4>
        <p>{{ image_names[forloop.index0] }}</p>
      </div>
    </div>
  {% endif %}
{% endfor %}
</div>

<br>

{% highlight python %}
# Test syntax highlighting for jekyll markdown
def hello_world():
    print("Hello world")
{% endhighlight %}

[link-one]: https://jekyllrb.com/docs/home
[link-two]: https://github.com/jekyll/jekyll
