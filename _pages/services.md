---
layout: default
permalink: /services/
---

<h1>
    The gamut of web experience is available to you as a client.
</h1>
<p>Don't know what you need? <a href="/contact-kyle/">Reach out and contact me for a consultation!</a></p>
{% for services in site.services %}
<div class="service-item">
    <h3><img src="{{ services.image }}"/>&nbsp;{{ services.name }}</h3>
</div>
<div id="{{ services.link }}" class="service-content" style="display: none; overflow: hidden;">{{services.content | markdownify }}</div>
{% endfor %}
<script>
var coll = document.getElementsByClassName("service-item");
var i;

for (i = 0; i < coll.length; i++) {
  coll[i].addEventListener("click", function() {
    this.classList.toggle("active");
    var content = this.nextElementSibling;
    if (content.style.display === "block") {
      content.style.display = "none";
    } else {
      content.style.display = "block";
    }
  });
}
</script>
