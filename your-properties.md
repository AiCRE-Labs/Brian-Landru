---
layout: default
title: Your Vacancies
---

<div class="centered-text">
  <div class="typing-effect" style="font-size: 18px;">
  <h2> Each of these properties has at least one vacancy. </h2>     
  </div>
</div> 

<div class="centered-text">
{% for post in site.posts %}
  <!-- <li> -->

  <div class="typing-effect" style="font-size: 16px;" style="animation-delay: 2.5s;">
  <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
  </div>
  <!-- </li> -->
{% endfor %}
</div>
