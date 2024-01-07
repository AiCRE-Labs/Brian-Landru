---
layout: default
title: Your Vacancies
permalink: /your-vacancies/
---


<h1><span id="properties"></span></h1>


<div class="centered-text">
{% for post in site.posts %}
  <!-- <li> -->

  <div class="typing-effect" style="font-size: 16px;" style="animation-delay: 2.5s;">
  <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
  </div>
  <!-- </li> -->
{% endfor %}
</div>


{% for property in site.data.properties %}
  {% if property[1].site_plan %}
    ![{{ property[0] }}]({{ property[1].site_plan | relative_url }})
  {% endif %}
{% endfor %}

<!-- Load library from the CDN -->
<script src="https://unpkg.com/typed.js@2.1.0/dist/typed.umd.js"></script>

<script>
  var hello = new Typed('#properties', {
    strings: ['Each of these properties has at least one vacancy:'],
    typeSpeed: 20,
    startDelay: 250,
    smartBackspace: false,
    loop: false,
    backDelay: 1000, // Delay period after the text is typed out
    showCursor: true,
    cursorChar: '|'
  });
</script>