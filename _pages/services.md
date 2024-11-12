---
layout: default
permalink: /services/
---
<style>
    .service-item 
    {
        cursor: pointer;
        border:1px solid #444;
        border-radius:9px;
        padding:15px 15px 7.5px 15px;
        margin-bottom:15px;
        background-color:#ccc;
    }
    .service-item.active
    {
        margin-bottom:0;
    }
    .service-item img
    {
        width:64px;
        height:64px;
    }
    .service-item img,
    .service-item h3
    {
        display: inline-block;
    }
    .service-content
    {
        /* text-align:center; */
        text-indent:15px;
        /* margin-top:15px; */
        border:1px solid black;
        border-bottom-right-radius:7.5px;
        border-bottom-left-radius:7.5px;
        border-top:0;
        width: 90%;
        margin: 0 auto 0 auto;
        
    }
    .service-content p 
    {
        margin-bottom:0;
        font-size:24px;
    }
    .service-item.active + .service-content
    {
        margin-bottom:15px;
    }
</style>
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
